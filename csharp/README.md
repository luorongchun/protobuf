
This directory contains the C# Protocol Buffers runtime library.

Usage
=====

The easiest way to use C# protocol buffers in your project is to use the [Google.ProtocolBuffers NuGet package](http://www.nuget.org/packages/Google.ProtocolBuffers/). This package is the legacy package for C# protocol buffers, but it will work fine with C# code generated by `protoc` if you use proto2 syntax (The API of the runtime library haven't changed so far).

*WARNING: If you specify `syntax = "proto3";` in your .proto files, the generated code won't necessarily work with the legacy NuGet package. So before we officially add proto3 support, always use `syntax = "proto2";` (the default) in your protos.*

We will definitely release a new NuGet package for the runtime library in the future. The new runtime library WILL contain significant semantic, backwardly-incompatible changes in proto handling (mostly because we will be adding proto3 support and we will be using that oportunity to make some design changes). So keep in mind that you will need to regenerate your proto files and switch to a new NuGet package once the new version of runtime library becomes available.

Building
========

Open the `src/ProtocolBuffers.sln` solution in Visual Studio. Click "Build solution" to build the solution. You should be able to run the NUnit test from Test Explorer (you might need to install NUnit Visual Studio add-in).

Supported Visual Studio versions are VS2013 (update 4) and VS2015. On Linux, you can also use Monodevelop 5.9 (older versions might work fine).

Proto2 & Proto3
===============

*WARNING: Only proto2 is supported for now, proto3 is under construction.*

C# protocol buffers are currently under development and you should expect semantic, backward-incompatible changes in the future.

Also, as of now, only proto2 is supported. Proto3 support for C# is currently in progress
(both design & implementation) and you should not expect any of the proto3 features to work. 
In fact, always use `syntax = "proto2";` in your .proto files for now, unless you are feeling like experimenting.

History of C# protobufs
=======================

This subtree was originally imported from https://github.com/jskeet/protobuf-csharp-port
and represents the latest development version of C# protobufs, that will now be developed
and maintained by Google. All the development will be done in open, under this repository
(https://github.com/google/protobuf).
