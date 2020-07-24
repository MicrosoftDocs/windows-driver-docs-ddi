---
UID: NF:wdfusb.WdfUsbInterfaceGetEndpointInformation
title: WdfUsbInterfaceGetEndpointInformation function (wdfusb.h)
description: The WdfUsbInterfaceGetEndpointInformation method retrieves information about a specified USB device endpoint and its associated pipe.
old-location: wdf\wdfusbinterfacegetendpointinformation.htm
tech.root: wdf
ms.assetid: c9e204db-f8fc-42e7-9a1b-f08099147ce7
ms.date: 02/26/2018
keywords: ["WdfUsbInterfaceGetEndpointInformation function"]
ms.keywords: DFUsbRef_fff1d755-32af-48d1-b9d6-faa8b118fa8d.xml, WdfUsbInterfaceGetEndpointInformation, WdfUsbInterfaceGetEndpointInformation method, kmdf.wdfusbinterfacegetendpointinformation, wdf.wdfusbinterfacegetendpointinformation, wdfusb/WdfUsbInterfaceGetEndpointInformation
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetEndpointInformation"
 - "WdfUsbInterfaceGetEndpointInformation"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfUsbInterfaceGetEndpointInformation
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetEndpointInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetEndpointInformation</b> method retrieves information about a specified USB device endpoint and its associated pipe.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


### -param EndpointIndex [in]

An index value that identifies an endpoint that is associated with the specified alternate setting of the specified interface. (This index value is not the endpoint address.)


### -param EndpointInfo [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure that the framework fills in.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



For more information about the <b>WdfUsbInterfaceGetEndpointInformation</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of endpoints that a USB interface supports and then calls <b>WdfUsbInterfaceGetEndpointInformation</b> for each endpoint.

```cpp
WDF_USB_PIPE_INFORMATION endPointInfo;
BYTE settingIndex, i;

settingIndex = 0;
numEndpoints = WdfUsbInterfaceGetNumEndpoints(
                                          UsbInterface,
                                          settingIndex
                                          );

for (i = 0; i < numEndpoints; i++){
    WDF_USB_PIPE_INFORMATION_INIT(&endPointInfo);
    WdfUsbInterfaceGetEndpointInformation(
                                          UsbInterface,
                                          settingIndex,
                                          i,
                                          &endPointInfo
                                          );

    //
    // Examine endpoint information here.
    //
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetnumendpoints">WdfUsbInterfaceGetNumEndpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
 

 

