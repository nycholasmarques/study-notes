Serialização é pegar um objeto que tem em memoria e persistir ele, seja em uma arquivo ou em alguma outra coisa.

**Serialização é a técnica que permite transformar o estado de um objeto em uma sequência bytes**. Depois que um objeto for serializado ele pode ser gravado (ou persistido) em um arquivo de dados e recuperado do arquivo e `desserializado` para recriar o objeto na memória. Uma vez serializado também o objeto pode ser salvo em arquivos ou transmitido remotamente usando uma rede de computadores através de um fluxo de dados ou stream via HTTP, via socket, entre outros.

Atributos do tipo static não são serializados.


Referencias: [DOCS](https://docs.oracle.com/javase/8/docs/api/java/io/Serializable.html) | [DEVMEDIA](https://www.devmedia.com.br/serializacao-de-objetos-em-java/23413)
