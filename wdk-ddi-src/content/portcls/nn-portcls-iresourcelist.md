---
UID: NN:portcls.IResourceList
title: IResourceList
author: windows-driver-content
description: The IResourceList interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time.
old-location: audio\iresourcelist.htm
old-project: audio
ms.assetid: e99ed3bc-368c-433f-ad40-98deda668c51
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IResourceList, IResourceList interface [Audio Devices], IResourceList interface [Audio Devices], described, audio.iresourcelist, audmp-routines_beb718b9-c62d-46b8-9147-c9e4aa7faa28.xml, portcls/IResourceList
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList interface


## -description


The <code>IResourceList</code> interface provides an abstraction of a configuration resource list, which is a list of the system hardware resources that the Plug and Play manager assigns to a device at startup time. The resources in the list can include interrupt vectors, DMA channels, I/O port addresses, and blocks of bus-relative memory addresses. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563856">Starting a Device in a Function Driver</a>.

The PortCls system driver implements the <code>IResourceList</code> interface and exposes it to adapter drivers. When PortCls calls an adapter driver's device-startup routine (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563849">Starting a Device</a>), it passes an <code>IResourceList</code> object as one of the call parameters. 

The header file portcls.h defines set of macros to simplify the handling of resource list objects. For each type of resource, the following four macros are defined:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG
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
    );</pre>
</td>
</tr>
</table></span></div>The following table shows the resource types for which these macros are defined.
<table>
<tr>
<th>Resource Type Name</th>
<th>Singular Form</th>
<th>Plural Form</th>
</tr>
<tr>
<td>
CmResourceTypePort

</td>
<td>
Port

</td>
<td>
Ports

</td>
</tr>
<tr>
<td>
CmResourceTypeInterrupt

</td>
<td>
Interrupt

</td>
<td>
Interrupts

</td>
</tr>
<tr>
<td>
CmResourceTypeMemory

</td>
<td>
Memory

</td>
<td>
Memories

</td>
</tr>
<tr>
<td>
CmResourceTypeDma

</td>
<td>
Dma

</td>
<td>
Dmas

</td>
</tr>
<tr>
<td>
CmResourceTypeDeviceSpecific

</td>
<td>
DeviceSpecific

</td>
<td>
DeviceSpecifics

</td>
</tr>
<tr>
<td>
CmResourceTypeBusNumber

</td>
<td>
BusNumber

</td>
<td>
BusNumbers

</td>
</tr>
<tr>
<td>
CmResourceTypePrivate

</td>
<td>
Private

</td>
<td>
Privates

</td>
</tr>
<tr>
<td>
CmResourceTypeAssignedResource

</td>
<td>
AssignedResource

</td>
<td>
AssignedResources

</td>
</tr>
<tr>
<td>
CmResourceTypeSubAllocateFrom

</td>
<td>
SubAllocateFrom

</td>
<td>
SubAllocateFroms

</td>
</tr>
</table> 

For the meanings of the resource type names in the left column above, see <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

The following table explicitly lists the four macros that portcls.h defines for each of the nine resource types. To the right of each macro is the equivalent call to an <code>IResourceList</code> method.
<table>
<tr>
<th>Macro</th>
<th>Equivalent IResourceList call</th>
</tr>
<tr>
<td>
NumberOfPorts()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypePort)

</td>
</tr>
<tr>
<td>
FindTranslatedPort(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypePort,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedPort(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypePort,(n))

</td>
</tr>
<tr>
<td>
AddPortFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypePort,(n))

</td>
</tr>
<tr>
<td>
NumberOfInterrupts()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeInterrupt)

</td>
</tr>
<tr>
<td>
FindTranslatedInterrupt(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeInterrupt,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedInterrupt(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeInterrupt,(n))

</td>
</tr>
<tr>
<td>
AddInterruptFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeInterrupt,(n))

</td>
</tr>
<tr>
<td>
NumberOfMemories()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeMemory)

</td>
</tr>
<tr>
<td>
FindTranslatedMemory(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeMemory,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedMemory(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeMemory,(n))

</td>
</tr>
<tr>
<td>
AddMemoryFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeMemory,(n))

</td>
</tr>
<tr>
<td>
NumberOfDmas()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeDma)

</td>
</tr>
<tr>
<td>
FindTranslatedDma(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeDma,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedDma(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeDma,(n))

</td>
</tr>
<tr>
<td>
AddDmaFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeDma,(n))

</td>
</tr>
<tr>
<td>
NumberOfDeviceSpecifics()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeDeviceSpecific)

</td>
</tr>
<tr>
<td>
FindTranslatedDeviceSpecific(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeDeviceSpecific,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedDeviceSpecific(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeDeviceSpecific,(n))

</td>
</tr>
<tr>
<td>
AddDeviceSpecificFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeDeviceSpecific,(n))

</td>
</tr>
<tr>
<td>
NumberOfBusNumbers()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeBusNumber)

</td>
</tr>
<tr>
<td>
FindTranslatedBusNumber(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeBusNumber,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedBusNumber(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeBusNumber,(n))

</td>
</tr>
<tr>
<td>
AddBusNumberFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeBusNumber,(n))

</td>
</tr>
<tr>
<td>
NumberOfDevicePrivates()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeDevicePrivate)

</td>
</tr>
<tr>
<td>
FindTranslatedDevicePrivate(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeDevicePrivate,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedDevicePrivate(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeDevicePrivate,(n))

</td>
</tr>
<tr>
<td>
AddDevicePrivateFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeDevicePrivate,(n))

</td>
</tr>
<tr>
<td>
NumberOfAssignedResources()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeAssignedResource)

</td>
</tr>
<tr>
<td>
FindTranslatedAssignedResource(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeAssignedResource,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedAssignedResource(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeAssignedResource,(n))

</td>
</tr>
<tr>
<td>
AddAssignedResourceFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeAssignedResource,(n))

</td>
</tr>
<tr>
<td>
NumberOfSubAllocateFroms()

</td>
<td>
NumberOfEntriesOfType(CmResourceTypeSubAllocateFrom)

</td>
</tr>
<tr>
<td>
FindTranslatedSubAllocateFrom(n)

</td>
<td>
FindTranslatedEntry(CmResourceTypeSubAllocateFrom,(n))

</td>
</tr>
<tr>
<td>
FindUntranslatedSubAllocateFrom(n)

</td>
<td>
FindUntranslatedEntry(CmResourceTypeSubAllocateFrom,(n))

</td>
</tr>
<tr>
<td>
AddSubAllocateFromFromParent(p,n)

</td>
<td>
AddEntryFromParent((p),CmResourceTypeSubAllocateFrom,(n))

</td>
</tr>
</table> 

