# Robot operating system

The **Robot Operating System** (commonly referred to as **ROS**) is a
middleware designed specifically for robotics applications. Its
development started in 2007 at Standford University from an idea of two
PhD students: Eric Berger and Keenan Wyrobek.  
The purpose of this robotics development platform was not to be the most
complete tool for developers, but rather to support code reuse in
robotics research and development. The idea came from the robotics
development methodologies of the time, which consisted of building the
required hardware and rewriting software that may have already been
written on other platforms (such as sensors/actuators drivers and
inter-process communication protocols).  
This approach was defined as *reinventing the wheel* because it
consisted of implementing already existing code snippets, resulting in a
consistent loss of time.  
The goal was to develop a tool and establish it as the standard
(nowadays ROS is called "*the linux of robotics*"), creating a community
of contributors to make it easy to use and completely transparent to the
user. The ROS philosophy imposes that the code to be reusable at its
most, in particular to be written to build other code on top of it. To
achieve this goal ROS is designed to be:

1.  **Thin**: The code can be composed of methods that don’t have a
    strong ROS dependency, thus it can be used on other robotics
    frameworks.

2.  **ROS-agnostic**: The dependency on ROS itself is minimal.

3.  **Language independent**: The programming language is almost free to
    choose for the developer.

4.  **Easy testing**: A set of tools for unit/integration testing is
    provided.

5.  **Scaling**: ROS can be used to develop large-scale applications.

6.  **Free and open-source**: The entire platform’s source code is
    publicly available.

## ROS

ROS is a combination of a meta-operating system, middleware and
programming model. It provides a set of libraries, tools and packages
along with elements typical of an operating system such as hardware
abstraction and low-level device control. It provides a communication
protocol and computation model, supporting different programming
languages including C++, Python and LISP.

### ROS Architecture

ROS is built on three conceptual levels:

1.  **Filesystem level**

2.  **Computation graph level**

3.  **Community level**

#### Filesystem level

The filesystem level comprehends every ROS related resource that can be
located on disk, including:

1.  **Packages**: The basic organizational element of ROS projects. It
    is a directory containing code, IDL and configuration files
    necessary to perform a specific task.

2.  **Metapackages**: Used to link loosely grouped packages using the
    package manifest.

3.  **Package manifest**: An “.xml” file containing the metadata of the
    package (such as developer and mantainer names, contact information
    and more) along with dependencies needed to run the package. The
    amount of information that can be found in this file is associated
    with the adherence to one of the following standards: REP-127,
    REP-140, REP-149.

4.  **Repositories**: Collection of packages.

5.  **Message types**: Data structures necessary for the communication
    among applications.

6.  **Service types**: Request/response data structures for ROS
    services.

#### Computation graph level

The computation graph represents the level at which data processing
occurs. It consists of processes that are interconnected in a
peer-to-peer topology, such that one-to-many and many-to-many
communication are possible.  
This level is composed of several fundamental elements that regulate the
interaction between processes of a ROS system. These elements include
nodes, messages, topics and services.

1.  **Nodes**: “Nodes are the processes that perform computation” . It
    represent the fundamental unit of the ROS code and should be
    designed to perform a single task. This is fundamental to maintain
    the modularity of the code, as ROS systems are typically composed of
    several of them.

2.  **Messages**: Messages are strictly-typed data structures, used by
    nodes to communicate with each other. These structures can consist
    of primitive data types (such as integers, booleans and arrays of
    the previous), more complex data types, or even other messages
    nested in an arbitrary fashion.

3.  **Topics**: Topics are named buses that allow nodes to send or
    receive information. A node may subscribe to a topic to receive data
    or publish over it to send information that other nodes may gather.
    A topic is instantiated when any node publishes to it, with the
    information exchange being mediated by messages. This
    publisher/subscriber model separates the information source and
    consumer, increasing modularity and scalability.

4.  **Services**:

All of these entities are managed by a lookup mechanism, called
**master**, whihc is needed to provide naming and registration services
to the nodes of the system to ensure that every entity of the graph is
properly connected to every other. The master is also responsible for
providing the **parameter server**.  
The parameter server is a storage facility for parameters. ROS
parameters are essentially values that may need dynamic reconfiguration.
Without a parameter server, the only way to reconfigure these values
would be by modifying the source code, but with it, parameters are
globally accessible and they can be retrieved, stored, modified and even
deleted.

#### Community level

**Inserire grafico in cui si mostrano i tre livelli concettuali di ROS
(tipo: alla base un hard disk, poi il computation graph e infine il
livello "community", con una stilizzazione di un gruppo di persone...)**

## ROS2

## G.N.C. architecture

## Gazebo simulator

### ROS2-GZ bridge
