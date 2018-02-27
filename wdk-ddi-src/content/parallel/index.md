---
UID: NA:parallel
ms.assetid: e507d2c6-0d63-3a57-be51-7db3ba17a47f
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Parallel.h header



This header is used by Parallel Ports. For more information, see
- [Parallel Ports](../_parports/index.md)

## Parallel Port Callback Routines

This section describes the types of callback routines that are supported by the system-supplied function driver for parallel ports.

A kernel-mode driver can use these callbacks to operate a parallel port. Some of the callback routines have equivalent device control requests, which are preferred over the callback routines.

An IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns a PARALLEL_PNP_INFORMATION structure, which contains pointers to the following types of callbacks:

An IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO request returns a PARALLEL_PORT_INFORMATION structure, which contains pointers to the following types of callbacks:

An IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request returns a PARALLEL_INTERRUPT_INFORMATION structure, which contains pointers to the following types of callbacks:

## Parallel Device Callback Routines


A client can use the parallel device callbacks to operate a parallel device attached to a parallel port. A client obtains pointers to these callbacks by using an IOCTL_INTERNAL_PARCLASS_CONNECT request, which returns a PARCLASS_INFORMATION structure. Note that some of the callbacks have equivalent device control requests, which are preferred over the following callbacks:

Send comments about this topic to Microsoft

