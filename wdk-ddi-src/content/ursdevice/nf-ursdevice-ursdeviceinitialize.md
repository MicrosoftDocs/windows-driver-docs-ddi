---
UID: NF:ursdevice.UrsDeviceInitialize
title: UrsDeviceInitialize function
author: windows-driver-content
description: Initializes a framework device object to support operations related to a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.
old-location: buses\ursdeviceinitialize.htm
old-project: usbref
ms.assetid: 8A9C76C0-70F5-4F65-A460-CCFCD236A242
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UrsDeviceInitialize, UrsDeviceInitialize function [Buses], buses.ursdeviceinitialize, ursdevice/UrsDeviceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsDeviceInitialize
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UrsDeviceInitialize function


## -description


Initializes a framework device object to support operations related to  a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


### -param Config [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a> structure that the client driver initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628021">URS_CONFIG_INIT</a>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the USB dual-role controller must call this method after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. 

The client driver calls this method in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> implementation.

During this call, the client driver-supplied event callback implementations are also registered by setting appropriate members of <a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a>. 

The method creates resource lists for host and function roles and the queues required to handle IOCTL requests that are sent to the controller. With each role switch operation, the current role's child device stack  is torn down and the device stack for the new role is loaded. The  <b>UrsDeviceInitialize</b> method retrieves identifying information that is used to build those device stacks. The method also retrieves information about the device from the underlying bus, such as ACPI.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>

EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterResourceRequirements;
EVT_URS_SET_ROLE EvtUrsSetRole;

EvtDriverDeviceAdd (
    _In_ WDFDRIVER Driver,
    _Inout_ PWDFDEVICE_INIT DeviceInit
    )
{
...

    WDFDEVICE device;
    NTSTATUS status;
    WDF_OBJECT_ATTRIBUTES attributes;
    URS_CONFIG ursConfig;
...
 
    status = UrsDeviceInitInitialize(DeviceInit);
    if (!NT_SUCCESS(status)) {
        //UrsDeviceInitInitialize failed.
        return status;
    }
   
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;attributes, DRIVER_CONTEXT);
    status = WdfDeviceCreate(&amp;DeviceInit, &amp;attributes, &amp;device);
    if (!NT_SUCCESS(status)) {
        // WdfDeviceCreate failed.
        return status;
    }
    URS_CONFIG_INIT(&amp;ursConfig, UrsHostInterfaceTypeXhci, EvtUrsFilterResourceRequirements);
    
    ursConfig.EvtUrsSetRole = EvtUrsSetRole;
    status = UrsDeviceInitialize(device, &amp;ursConfig);

    if (!NT_SUCCESS(status)) {
        // UrsDeviceInitialize failed.
        return status;

    }

...

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628021">URS_CONFIG_INIT</a>
 

 

