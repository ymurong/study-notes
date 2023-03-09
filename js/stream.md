## Types of Streams
In Node, there are four different types of streams:

- Readable streams → To create a stream of data for reading (say, reading a large file in chunks).
- Writable streams → To create a stream of data for writing (say, writing a large amount of data to a file).
- Duplex streams → To create a stream that is both readable and writable at the same time. We can read and write to a duplex stream (say, a socket connection between a client and a server).
- Transform streams → To create a stream that is readable and writable, but the data can be modified while reading and writing to the stream (say, compressing data by the client and server before while requesting).
