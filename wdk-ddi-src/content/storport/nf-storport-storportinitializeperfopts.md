---
UID: NF:storport.StorPortInitializePerfOpts
title: StorPortInitializePerfOpts function
author: windows-driver-content
description: The StorPortInitializePerfOpts function initializes the performance optimizations that both the miniport driver and the Storport driver support using a PERF_CONFIGURATION_DATA structure.
old-location: storage\storportinitializeperfopts.htm
old-project: storage
ms.assetid: fbaf864c-d499-456c-be3b-b486c637877e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortInitializePerfOpts
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortInitializePerfOpts
req.alt-loc: Storport.h
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInitializePerfOpts function



## -description
The <b>StorPortInitializePerfOpts</b> function initializes the performance optimizations that both the miniport driver and the Storport driver support using a <a href="..\storport\ns-storport-_perf_configuration_data.md">PERF_CONFIGURATION_DATA</a> structure.



## -syntax

````
ULONG StorPortInitializePerfOpts(
  _In_    PVOID                    HwDeviceExtension,
  _In_    BOOLEAN                  Query,
  _Inout_ PPERF_CONFIGURATION_DATA PerfConfigData
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This parameter must not be <b>NULL</b>.


### -param Query [in]

If set to <b>TRUE</b>, Storport will set the flags in <i>PerfConfigData</i> corresponding to the optimizations Storport supports. If set to <b>FALSE</b>, Storport will initialize the optimizations specified by the flags in <i>PerfConfigData</i>.


### -param PerfConfigData [in, out]

A pointer to a PERF_CONFIGURATION_DATA structure that is supplied by the miniport driver. This parameter must not be <b>NULL</b>.


## -returns
StorPortInitializePerfOpts returns one of the following status values:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the performance optimization settings have been applied.

Or if <i>Query</i> is set to <b>TRUE</b>,  the <b>Flags</b> member of the structure pointed to by <i>PerfConfigData</i> contains the supported flags.
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>The miniport driver set a flag in <i>PerfConfigData</i> that Storport did not recognize, or the miniport driver has called this routine from outside the miniport-driver-supplied <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Unable to allocate internal structures to support the requested optimizations.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>Either the <i>HwDeviceExtension</i> parameter or the <i>PerfConfigData</i> parameter was <b>NULL</b>.

 


## -remarks

    The miniport driver can call <b>StorPortInitializePerfOpts</b> only during the miniport-supplied   <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine or <a href="..\storport\nc-storport-hw_passive_initialize_routine.md">HwStorPassiveInitializeRoutine</a> routine.
   

Available performance optimizations depend on the version of <a href="..\storport\ns-storport-_perf_configuration_data.md">PERF_CONFIGURATION_DATA</a>. Setting the <b>Version</b> member to <b>STOR_PERF_VERSION</b> will allow all supported optimizations to be selected.


## -see-also
<dl>
<dt>
<a href="..\storport\ns-storport-_perf_configuration_data.md">PERF_CONFIGURATION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializePerfOpts function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

