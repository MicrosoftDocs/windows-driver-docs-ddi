---
UID: NF:wdfdmaenabler.WdfDmaEnablerConfigureSystemProfile
title: WdfDmaEnablerConfigureSystemProfile function
author: windows-driver-content
description: The WdfDmaEnablerConfigureSystemProfile method configures the hardware-specific settings for a system-mode DMA enabler and completes the resource initialization.
old-location: wdf\wdfdmaenablerconfiguresystemprofile.htm
old-project: wdf
ms.assetid: 3374EBB8-F43A-4A2A-92AC-623B39F5EFA0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaEnablerConfigureSystemProfile, WdfDmaEnablerConfigureSystemProfile method, kmdf.wdfdmaenablerconfiguresystemprofile, wdf.wdfdmaenablerconfiguresystemprofile, wdfdmaenabler/WdfDmaEnablerConfigureSystemProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
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
-	WdfDmaEnablerConfigureSystemProfile
product:
- Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerConfigureSystemProfile function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDmaEnablerConfigureSystemProfile</b> method 
  configures the hardware-specific settings for a system-mode DMA enabler and completes the resource initialization.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.


### -param ProfileConfig [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure. Drivers must initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh439499">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>.


### -param ConfigDirection [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551288">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551295">WDF_DMA_PROFILE</a> value for this enabler is not <b>WdfDmaProfileSystemDuplex</b>, the framework ignores this parameter.


## -returns



<b>WdfDmaEnablerConfigureSystemProfile</b> returns STATUS_SUCCESS if the operation succeeds.  Otherwise, the method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The driver requested a DMA configuration that is not supported on the current operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied NULL in the <i>ProfileConfig</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <b>Size</b> member of the structure pointed to by the <i>ProfileConfig</i> parameter is not equal to the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>DmaDescriptor</b> member of the structure pointed to by the <i>ProfileConfig</i> parameter is NULL or the <i>ConfigDirection</i> parameter contains an invalid value.

</td>
</tr>
</table>
 




## -remarks



Before calling <b>WdfDmaEnablerConfigureSystemProfile</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a> to create the enabler object.

A driver typically calls <b>WdfDmaEnablerConfigureSystemProfile</b> from its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function.

If your driver specified a duplex profile when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>, the <b>WdfDmaEnablerConfigureSystemProfile</b> method's <i>ConfigDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the <b>DMA_ADAPTER</b> structure for write operations.

If the DMA enabler is a duplex enabler, the driver must initialize a particular direction before it can use it.  

 If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b>.
 


#### Examples

The following code example is from a driver's <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function. This example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure and calls <b>WdfDmaEnablerConfigureSystemProfile</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
WDF_DMA_SYSTEM_PROFILE_CONFIG systemDmaConfig;  
PHYSICAL_ADDRESS pa;  
 
pa.QuadPart = 0;  
  
WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT(&amp;systemDmaConfig,   
                                   pa,  
                                   Width8Bits,  
                                   partial);  
  
systemDmaConfig.DemandMode = true;  
 
ntStatus = WdfDmaEnablerConfigureSystemProfile(fdoExtension-&gt;DmaEnabler,   
                                               &amp;systemDmaConfig,   
                                               WdfDmaDirectionReadFromDevice);  
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://msdn.microsoft.com/b01efb50-a3b2-4ffd-83e6-daa0ebbc6484">WDF_DMA_ENABLER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439499">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>
 

 

