---
UID: NA:acxstreams
title: acxstreams.h header
ms.date:  06/16/2021
keywords: ["acxstreams.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: audio
f1_keywords:
 - acxstreams
 - acxstreams/acxstreams
api_name:
 - acxstreams
---

# acxstreams.h header


## -description

This header is used by the ACX audio class extensions.

For more information, see:

- [Audio](../_audio/index.md)<br><br>


### Definitions 

*Endpoint Audio Path* - A group of Circuit objects connected together to represent a single endpoint. The Circuit objects can come from different drivers or from the same driver. 

*Circuit* - A driver component representing a portion of the audio path. The circuit represents an existing endpoint and its capabilities. 

*Element* - A subcomponent of a Circuit or Stream, representing a target for ACX properties or events. This could be a Volume or Jack element on an Amp circuit, or a Mode element on a DSP circuit 

*Stream* -  A driver component that’s created to represent an audio stream, created by a Circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.  

*Head Circuit* - The circuit in the Endpoint Audio Path that registers the SINK/SOURCE circuit element. In the case of a single-stack driver model, there would be a single Circuit for the Endpoint Audio Path. 

### Header elements
