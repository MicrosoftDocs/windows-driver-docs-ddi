---
UID: NF:storport.StorPortInitializePerfOpts
title: StorPortInitializePerfOpts function (storport.h)
description: The StorPortInitializePerfOpts function initializes the performance optimizations that both the miniport driver and the Storport driver support using a PERF_CONFIGURATION_DATA structure.
old-location: storage\storportinitializeperfopts.htm
tech.root: storage
ms.assetid: fbaf864c-d499-456c-be3b-b486c637877e
ms.date: 03/29/2018
ms.keywords: StorPortInitializePerfOpts, StorPortInitializePerfOpts function [Storage Devices], storage.storportinitializeperfopts, storport/StorPortInitializePerfOpts, storprt_84998f54-51fe-40fd-a8cc-ba0367a592ce.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortInitializePerfOpts"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortPerfOpts
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- StorPortInitializePerfOpts
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitializePerfOpts function


## -description


The <b>StorPortInitializePerfOpts</b> function initializes the performance optimizations that both the miniport driver and the Storport driver support using a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-_perf_configuration_data">PERF_CONFIGURATION_DATA</a> structure.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This parameter must not be <b>NULL</b>.


### -param Query [in]

If set to <b>TRUE</b>, Storport will set the flags in <i>PerfConfigData</i> corresponding to the optimizations Storport supports. If set to <b>FALSE</b>, Storport will initialize the optimizations specified by the flags in <i>PerfConfigData</i>.


### -param PerfConfigData [in, out]

A pointer to a PERF_CONFIGURATION_DATA structure that is supplied by the miniport driver. This parameter must not be <b>NULL</b>.


## -returns



StorPortInitializePerfOpts returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the performance optimization settings have been applied.

Or if <i>Query</i> is set to <b>TRUE</b>,  the <b>Flags</b> member of the structure pointed to by <i>PerfConfigData</i> contains the supported flags.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver set a flag in <i>PerfConfigData</i> that Storport did not recognize, or the miniport driver has called this routine from outside the miniport-driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_initialize">HwStorInitialize</a> routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Unable to allocate internal structures to support the requested optimizations.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>HwDeviceExtension</i> parameter or the <i>PerfConfigData</i> parameter was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks




    The miniport driver can call <b>StorPortInitializePerfOpts</b> only during the miniport-supplied   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_initialize">HwStorInitialize</a> routine or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a> routine.
   

Available performance optimizations depend on the version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-_perf_configuration_data">PERF_CONFIGURATION_DATA</a>. Setting the <b>Version</b> member to <b>STOR_PERF_VERSION</b> will allow all supported optimizations to be selected.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/ns-storport-_perf_configuration_data">PERF_CONFIGURATION_DATA</a>
 

 

