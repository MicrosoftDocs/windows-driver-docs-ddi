---
UID: NF:wdfwmi.WdfWmiInstanceFireEvent
title: WdfWmiInstanceFireEvent function
author: windows-driver-content
description: The WdfWmiInstanceFireEvent method sends a WMI event to WMI clients that have registered to receive event notification.
old-location: wdf\wdfwmiinstancefireevent.htm
old-project: wdf
ms.assetid: 7bef79ab-78d6-47b6-a3f4-d9733ffcb53d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfWmiInstanceFireEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfWmiInstanceFireEvent
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceFireEvent function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceFireEvent</b> method sends a WMI event to WMI clients that have registered to receive event notification.



## -syntax

````
NTSTATUS WdfWmiInstanceFireEvent(
  _In_     WDFWMIINSTANCE WmiInstance,
  _In_opt_ ULONG          EventDataSize,
  _In_opt_ PVOID          EventData
);
````


## -parameters

### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


### -param EventDataSize [in, optional]

The size, in bytes, of the event data that <i>EventData</i> points to.


### -param EventData [in, optional]

A pointer to the event data, or <b>NULL</b> if there is no event data.


## -returns
<b>WdfWmiInstanceFireEvent</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The framework's attempt to communicate with WMI failed.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The event data buffer was too large.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Your driver should call <b>WdfWmiInstanceFireEvent</b> only if a WMI client has registered for event notification. The driver can determine if it should call <b>WdfWmiInstanceFireEvent</b> by providing an <a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a> callback function or calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>.

The driver should place its event-specific data, if any, in the buffer that the <i>EventData</i> parameter points to. The framework adds all of the necessary WMI header information.

For more information about the <b>WdfWmiInstanceFireEvent</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

The following code example sends a WMI event to WMI clients. 


## -see-also
<dl>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt_wdf_wmi_provider_function_control.md">EvtWmiProviderFunctionControl</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiproviderisenabled.md">WdfWmiProviderIsEnabled</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceFireEvent method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

