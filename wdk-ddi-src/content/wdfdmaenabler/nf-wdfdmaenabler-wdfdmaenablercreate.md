---
UID: NF:wdfdmaenabler.WdfDmaEnablerCreate
title: WdfDmaEnablerCreate function
author: windows-driver-content
description: The WdfDmaEnablerCreate method creates a DMA enabler object.
old-location: wdf\wdfdmaenablercreate.htm
old-project: wdf
ms.assetid: 750c9293-7662-41e0-9a2a-5c19e49ad20e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_f0ec3598-ae92-45b3-98af-b2ce590f996f.xml, WdfDmaEnablerCreate, WdfDmaEnablerCreate method, kmdf.wdfdmaenablercreate, wdf.wdfdmaenablercreate, wdfdmaenabler/WdfDmaEnablerCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaEnablerCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerCreate</b> method creates a DMA enabler object. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Config [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure. Drivers must initialize this structure by calling <a href="https://msdn.microsoft.com/b01efb50-a3b2-4ffd-83e6-daa0ebbc6484">WDF_DMA_ENABLER_CONFIG_INIT</a>.


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the new DMA enabler object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param DmaEnablerHandle [out]

A handle to a new DMA enabler object.  


## -returns



<b>WdfDmaEnablerCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

        There was insufficient memory to construct a new DMA enabler object.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The driver requested DMA version 3 on an operating system earlier than Windows 8.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfDmaEnablerCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Framework-based drivers must call <b>WdfDmaEnablerCreate</b> before creating DMA transactions for a device.

Before a driver calls <b>WdfDmaEnablerCreate</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>.

The framework device object that the <i>Device</i> parameter of <b>WdfDmaEnablerCreate</b> specifies always becomes the parent object for the new DMA enabler object. If the driver specifies a different parent in the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure, the framework ignores this value. The framework deletes the DMA enabler object when it deletes the parent object.

When called with a  <i>Config</i> parameter that requests a system-mode DMA profile, <b>WdfDmaEnablerCreate</b> creates a partially initialized DMA enabler.  The driver must subsequently call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451108">WdfDmaEnablerConfigureSystemProfile</a> to set up the DMA settings for the underlying channels.

For more information about DMA enabler objects and <b>WdfDmaEnablerCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">PLX9x5x</a> sample driver. This example sets a device's requirement for buffer alignment, initializes a WDF_DMA_ENABLER_CONFIG structure, and calls <b>WdfDmaEnablerCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// PLx PCI9656 DMA_TRANSFER_ELEMENTS must be 16-byte aligned.
//
WdfDeviceSetAlignmentRequirement(
                                 DevExt-&gt;WdfDevice,
                                 PCI9656_DTE_ALIGNMENT_16
                                 );

//
// Create a new DMA enabler object instance. 
// Use scatter/gather, 64-bit addresses, and duplex-type profile.
//
{
    WDF_DMA_ENABLER_CONFIG   dmaConfig;
    WDF_DMA_ENABLER_CONFIG_INIT(
                                &amp;dmaConfig,
                                WdfDmaProfileScatterGather64Duplex,
                                DevExt-&gt;MaximumTransferLength
                                );
    status = WdfDmaEnablerCreate(
                                 DevExt-&gt;WdfDevice,
                                 &amp;dmaConfig,
                                 WDF_NO_OBJECT_ATTRIBUTES,
                                 &amp;DevExt-&gt;DmaEnabler
                                 );
    if (!NT_SUCCESS (status)) {
        // Cannot continue, so release device resources.
        return status;
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://msdn.microsoft.com/b01efb50-a3b2-4ffd-83e6-daa0ebbc6484">WDF_DMA_ENABLER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>
 

 

