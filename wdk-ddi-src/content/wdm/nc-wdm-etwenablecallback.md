---
UID: NC:wdm.ETWENABLECALLBACK
title: ETWENABLECALLBACK (wdm.h)
description: The EtwEnableCallback function is an optional driver-supplied callback function that is used to receive enable or disable notifications.
old-location: devtest\etwenablecallback.htm
tech.root: devtest
ms.assetid: 5953a3ae-b130-42fd-9dc8-974d15c6dfc5
ms.date: 02/23/2018
keywords: ["ETWENABLECALLBACK callback function"]
ms.keywords: EtwEnableCallback, EtwEnableCallback callback function [Driver Development Tools], PETWENABLECALLBACK, PETWENABLECALLBACK callback, devtest.etwenablecallback, etw_km_6405d4d5-382c-4950-9b91-0cb224a3d069.xml, wdm/EtwEnableCallback
f1_keywords:
 - "wdm/EtwEnableCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- EtwEnableCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# ETWENABLECALLBACK callback function


## -description


The <b>EtwEnableCallback</b> function is an optional driver-supplied callback function that is used to receive enable or disable notifications. 


## -parameters




### -param SourceId [in]

The GUID that identifies the session that enabled the provider. 


### -param ControlCode


### -param Level [in]

The level at which the event is enabled. This parameter is a provider-defined value that specifies the verboseness of the events that the provider writes. The provider must write the event if this value is less than or equal to the level value that the event defines. 

This value is passed in the <i>Level</i> parameter of the <a href="https://go.microsoft.com/fwlink/p/?linkid=103398">EnableTraceEx</a> function or the <i>EnableLevel</i> parameter of the <a href="https://go.microsoft.com/fwlink/p/?linkid=103399">EnableTrace</a> function.


### -param MatchAnyKeyword [in]

The bitmask of keywords that the provider uses to determine the category of events that it writes. 

This value is passed in the <i>MatchAnyKeyword</i> parameter of the <a href="https://go.microsoft.com/fwlink/p/?linkid=103398">EnableTraceEx</a> function or the <i>EnableFlag</i> parameter of the <a href="https://go.microsoft.com/fwlink/p/?linkid=103399">EnableTrace</a> function. <i>MatchAnyKeyword</i> is a 64-bit value and is basically an extended version of the 32-bit <i>EnableFlag</i>.


### -param MatchAllKeyword [in]

This bitmask additionally restricts the category of events that the provider writes. 

This value is passed in the <i>MatchAllKeywords</i> parameter of the <b>EnableTraceEx</b> function.


### -param FilterData [in, optional]

The provider-defined data. This parameter is optional. The provider determines the layout of the data and its purpose. For example, the provider can use this data to additionally filter the events that it writes or use it to perform some calculations before writing the events. For detailed information, see <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/ns-evntprov-_event_filter_descriptor">Event Filter Descriptor</a>.


### -param CallbackContext [in, out, optional]

The context of the callback function that is defined when the provider called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister">EtwRegister</a> to register itself. This parameter is optional.


#### - IsEnabled [in]

The parameter indicates whether the provider is being enabled or disabled. The value is <b>TRUE</b> if the session enabled the provider; otherwise, it is <b>FALSE</b>.


## -remarks



Use the EtwRegister function to specify a pointer to the <b>EtwEnableCallback </b>function.

Use the <i>FilterData</i> parameter of the callback function to supply the provider with sophisticated filtering abilities. The <b>EtwEnableCallback </b>function does not replace the enable-status function calls (<b>EtwEventEnabled</b> and <b>EtwProviderEnabled</b>). However, it serves as a supplement to them. However, unless your level and keywords are currently enabled, the event will not be written, regardless of the <i>FilterData</i> that the callback function provides.

Callers of <b>EtwEnableCallback</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://go.microsoft.com/fwlink/p/?linkid=103399">EnableTrace</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=103398">EnableTraceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etweventenabled">EtwEventEnabled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwproviderenabled">EtwProviderEnabled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister">EtwRegister</a>



<a href="https://docs.microsoft.com/windows/desktop/api/evntprov/ns-evntprov-_event_filter_descriptor">Event Filter Descriptor</a>
 

 

