---
UID: NN:portcls.IResourceList
title: IResourceList
author: windows-driver-content
description: The IResourceList interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time.
old-location: audio\iresourcelist.htm
old-project: audio
ms.assetid: e99ed3bc-368c-433f-ad40-98deda668c51
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IResourceList
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList interface



## -description
The <code>IResourceList</code> interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time. The resources in the list can include interrupt vectors, DMA channels, I/O port addresses, and blocks of bus-relative memory addresses. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563856">Starting a Device in a Function Driver</a>.

The PortCls system driver implements the <code>IResourceList</code> interface and exposes it to adapter drivers. When PortCls calls an adapter driver's device-startup routine (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563849">Starting a Device</a>), it passes an <code>IResourceList</code> object as one of the call parameters. 

The header file portcls.h defines set of macros to simplify the handling of resource list objects. For each type of resource, the following four macros are defined:



## -syntax

````
ULONG
  NumberOfpluralresourcename(
    void
 ); 

PCM_PARTIAL_RESOURCE_DESCRIPTOR
  FindTranslatedsingularresourcename(
    ULONG  Index
    );

PCM_PARTIAL_RESOURCE_DESCRIPTOR
  FindUntranslatedsingularresourcename(
    ULONG  Index
    );

NTSTATUS
  AddsingularresourcenameFromParent(
    PRESOURCELIST  Parent,
    ULONG  Index
    );
````


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IResourceList</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks
