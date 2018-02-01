---
UID: NF:portcls.IPortWaveRTStream.GetPhysicalPagesCount
title: IPortWaveRTStream::GetPhysicalPagesCount method
author: windows-driver-content
description: The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpagescount.htm
old-project: audio
ms.assetid: 8126af29-a7ee-4ab7-8902-45b4baf33b9e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GetPhysicalPagesCount method [Audio Devices], IPortWaveRTStream interface, portcls/IPortWaveRTStream::GetPhysicalPagesCount, audio.iportwavertstream_getphysicalpagescount, audmp-routines_bdc74102-0337-436b-b3ac-68187fb323a4.xml, IPortWaveRTStream::GetPhysicalPagesCount, GetPhysicalPagesCount method [Audio Devices], IPortWaveRTStream interface [Audio Devices], GetPhysicalPagesCount method, GetPhysicalPagesCount, IPortWaveRTStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortWaveRTStream.GetPhysicalPagesCount
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortWaveRTStream::GetPhysicalPagesCount method


## -description


The <code>GetPhysicalPagesCount</code> method returns the count of the physical pages in a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>).


## -syntax


````
ULONG GetPhysicalPagesCount(
  [in] PMDL MemoryDescriptorList
);
````


## -parameters




### -param MemoryDescriptorList [in]

Pointer to the MDL.


## -returns


<code>GetPhysicalPagesCount</code> method returns the count of physical pages in the MDL.



## -remarks


The miniport driver uses this call to determine the number of physical pages that are contained within an MDL. The count is typically used in the process of programming the DMA hardware.



## -see-also

<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536928">IPortWaveRTStream::GetPhysicalPageAddress</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::GetPhysicalPagesCount method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

