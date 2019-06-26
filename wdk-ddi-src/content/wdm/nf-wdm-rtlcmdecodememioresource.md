---
UID: NF:wdm.RtlCmDecodeMemIoResource
title: RtlCmDecodeMemIoResource function (wdm.h)
description: The RtlCmDecodeMemIoResource routine provides the starting address and length of a CM_PARTIAL_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses.
old-location: kernel\rtlcmdecodememioresource.htm
tech.root: kernel
ms.assetid: cc2394ce-128e-46a2-8688-a71851af06cf
ms.date: 04/30/2018
ms.keywords: RtlCmDecodeMemIoResource, RtlCmDecodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_da737a74-2fce-4731-b24d-9014272991f1.xml, kernel.rtlcmdecodememioresource, wdm/RtlCmDecodeMemIoResource
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlCmDecodeMemIoResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCmDecodeMemIoResource function


## -description


The <b>RtlCmDecodeMemIoResource</b> routine provides the starting address and length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a range of memory or I/O port addresses. 


## -parameters




### -param Descriptor [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to provide the starting address and length for.


### -param Start [out, optional]

A pointer to a variable that receives the starting address of the range of memory or I/O port addresses.


## -returns



<b>RtlCmDecodeMemIoResource</b> returns the length of the address range, in bytes.




## -remarks



The <b>Type</b> member of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure must be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcmencodememioresource">RtlCmEncodeMemIoResource</a>
 

 

