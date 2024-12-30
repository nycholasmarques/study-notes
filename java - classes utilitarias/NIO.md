## **Java NIO**

O Java NIO foi adicionado no JDK 1.4 nos pacotes _java.nio_, _java.nio.channels_ e _java.nio.charset_. Ao invés de trabalhar com fluxos, o NIO utiliza duas novas abstrações para executar as operações de I/O: Buffers e Canais (_Channels_). tornando-o mais rápido e adequado para aplicativos de alto desempenho. O objetivo do NIO não é substituir o Java IO, mas sim complementá-lo ao oferecer soluções para as limitações apontadas anteriormente.

### Principais Funcionalidades Essenciais

1. **Buffers**: Estruturas para armazenar e manipular dados.
2. **Channels**: Objetos para realizar operações de leitura e escrita.
3. **Path e Files**: Manipulação moderna de caminhos e arquivos.
4. **Selectors**: Permitem gerenciar múltiplos canais de forma não bloqueante.

## Buffers

Os buffers (`ByteBuffer`, `CharBuffer`, etc.) são usados para armazenar dados de entrada/saída.

Um buffer no Java ==é uma área de armazenamento temporário na memória do computador que guarda dados enquanto eles estão sendo transferidos==

Exemplo: Uso do `ByteBuffer`

```java
import java.nio.ByteBuffer;

public class BufferExample {
    public static void main(String[] args) {
        ByteBuffer buffer = ByteBuffer.allocate(10); // Aloca 10 bytes
        buffer.put((byte) 1);
        buffer.put((byte) 2);
        buffer.put((byte) 3);

        System.out.println("Posição antes de flip: " + buffer.position());
        buffer.flip(); // Prepara o buffer para leitura

        while (buffer.hasRemaining()) {
            System.out.println("Valor: " + buffer.get());
        }
    }
}
```

## Channels

Os canais (`FileChannel`, `SocketChannel`, etc.) são a base para transferir dados entre buffers e fontes externas.

Um channel no Java ==é um conjunto de contêineres, que são blocos de dados nomeados que servem para passar informações entre programas==.

Exemplo: Leitura com `FileChannel`
```java
import java.io.RandomAccessFile;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;

public class FileChannelExample {
    public static void main(String[] args) {
        try (RandomAccessFile file = new RandomAccessFile("example.txt", "r");
             FileChannel channel = file.getChannel()) {

            ByteBuffer buffer = ByteBuffer.allocate(1024);
            int bytesRead = channel.read(buffer);

            while (bytesRead != -1) {
                buffer.flip(); // Prepara para leitura
                while (buffer.hasRemaining()) {
                    System.out.print((char) buffer.get());
                }
                buffer.clear(); // Prepara para próxima leitura
                bytesRead = channel.read(buffer);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Path e Files

As classes `Path` e `Files` oferecem uma API moderna para trabalhar com arquivos e diretórios.
Exemplo: Criando e Listando Arquivos com `Files`
```java
import java.nio.file.*;

public class FilesExample {
    public static void main(String[] args) {
        try {
            Path path = Paths.get("example.txt");
            
            // Criar um arquivo
            if (!Files.exists(path)) {
                Files.createFile(path);
                System.out.println("Arquivo criado: " + path.getFileName());
            }

            // Listar arquivos em um diretório
            Path dir = Paths.get(".");
            Files.list(dir)
                 .forEach(System.out::println);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Selectors

Os selectors permitem monitorar múltiplos canais para eventos (leitura, escrita, etc.), muito usados em servidores não bloqueantes.
Exemplo: Monitorando Múltiplos Canais (Simples)
```java
import java.nio.channels.*;
import java.nio.*;
import java.net.*;
import java.util.Iterator;

public class SelectorExample {
    public static void main(String[] args) {
        try (Selector selector = Selector.open()) {
            ServerSocketChannel serverChannel = ServerSocketChannel.open();
            serverChannel.configureBlocking(false);
            serverChannel.socket().bind(new InetSocketAddress(8080));
            serverChannel.register(selector, SelectionKey.OP_ACCEPT);

            while (true) {
                selector.select(); // Espera por eventos
                Iterator<SelectionKey> keys = selector.selectedKeys().iterator();

                while (keys.hasNext()) {
                    SelectionKey key = keys.next();
                    keys.remove();

                    if (key.isAcceptable()) {
                        SocketChannel clientChannel = serverChannel.accept();
                        clientChannel.configureBlocking(false);
                        clientChannel.register(selector, SelectionKey.OP_READ);
                        System.out.println("Cliente conectado!");
                    } else if (key.isReadable()) {
                        SocketChannel clientChannel = (SocketChannel) key.channel();
                        ByteBuffer buffer = ByteBuffer.allocate(256);
                        clientChannel.read(buffer);
                        System.out.println("Recebido: " + new String(buffer.array()).trim());
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```
## Vantagens e desvantagens

**Vantagens**

A maior vantagem do NIO talvez seja a sua capacidade de realizar I/O não bloqueante, algo que não era possível na API mais antiga. Isso significa que a aplicação é capaz de gerenciar várias operações de I/O em uma única thread, sem precisar esperar pela finalização de cada operação, o que é essencial para a escalabilidade de aplicações como servidores. A implementação do NIO também é mais próxima do sistema operacional do que o Java IO, o que pode significar um menor overhead nas operações de I/O e consequentemente maior desempenho, caso a sua aplicação faça uso intensivo de entrada e saída.

**Desvantagens**

A flexibilidade e escalabilidade do NIO tem um custo bem evidente: complexidade. Comparado com o Java IO, a API do NIO é claramente mais complexa e difícil de usar. Embora seja possível realizar operações simples de I/O utilizando quase que exclusivamente o NIO, o código resultante é quase sempre maior, mais confuso e difícil de manter.
## Resumo

- **`Buffer`**: Armazena dados para leitura e escrita (ex.: `ByteBuffer`, `CharBuffer`).
- **`Channel`**: Conecta buffers a arquivos, sockets ou dispositivos (ex.: `FileChannel`, `SocketChannel`).
- **`Path`**: Representa um caminho de arquivo ou diretório.
- **`Files`**: Realiza operações utilitárias em arquivos e diretórios.
- **`Selector`**: Gerencia múltiplos canais de forma não bloqueante.