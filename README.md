# Assignment-12.3

1 What is meant by FlumeNG ?
ans : Flume NG is a refactoring of Flume and was originally tracked in FLUME-728. From the JIRA's description:
To solve certain known issues and limitations, Flume requires a refactoring of some core classes and systems. This bug is a parent issue to track the development of a "Flume NG" - a poorly named, but necessary refactoring. Subtasks should be added to track individual systems and components.
The following known issues are specifically to be addressed:
Code complexity; Flume has evolved over the last few years and has a fair amount of extraneous code.
Core component lifecycle standardization and control code (e.g. anything that can be start()ed or stop()ed, sources, sinks).
(Static) Configuration access throughout the code base.
Drastic simplification of common data paths (e.g. durability as an element of the source rather than a disconnected sink).
Heartbeat and master rearchitecture.
Renaming packages to org.apache.flume.
This is a large and far reaching set of tasks. The intent is to perform this work in a branch as to not disrupt immediate releases or short term forthcoming releases while still allowing open development in the community.

2 Can Flume provides 100 % reliability to the data flow?
ans : YES, it provide end-to-end reliability of the flow. By default flume uses a transactional approach  in the data flow. Souces and sinks encapsulated in a transactional repository provided by the channels. This channel is responsible to pass reliably end-to-end in the flow. So, it provides 100% reliability to the data flow.

3 Can Flume can distributes data to multiple destinations?
ans : Yes, it supports multiplexing flow. The event flows from one source to multiple channels and multiple destinations. It's achieved by defining a flow multiplexer.

4 Explain about the different channel types in Flume. And which channel type is
faster?
ans : The 3 different built in channel types available in Flume are-

MEMORY Channel – Events are read from the source into memory and passed to the sink.
JDBC Channel – JDBC Channel stores the events in an embedded Derby database.
FILE Channel – File Channel writes the contents to a file on the file system after reading the event from a source. The file is deleted only  after the contents are successfully delivered to the sink.

MEMORY Channel is the fastest channel among the three however has the risk of data loss. The channel that you choose completely depends on the nature of the big data application and the value of each event.


