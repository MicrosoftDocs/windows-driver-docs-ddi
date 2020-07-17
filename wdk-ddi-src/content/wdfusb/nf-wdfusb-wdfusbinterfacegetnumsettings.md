---
UID: NF:wdfusb.WdfUsbInterfaceGetNumSettings
title: WdfUsbInterfaceGetNumSettings function (wdfusb.h)
description: The WdfUsbInterfaceGetNumSettings method returns the number of alternate settings that a specified USB interface supports.
old-location: wdf\wdfusbinterfacegetnumsettings.htm
tech.root: wdf
ms.assetid: 07de1b64-bafb-4b5b-8ef3-24b87ae0c273
ms.date: 02/26/2018
keywords: ["WdfUsbInterfaceGetNumSettings function"]
ms.keywords: DFUsbRef_5515a8bf-1a43-434c-9806-75393a17fdf5.xml, WdfUsbInterfaceGetNumSettings, WdfUsbInterfaceGetNumSettings method, kmdf.wdfusbinterfacegetnumsettings, wdf.wdfusbinterfacegetnumsettings, wdfusb/WdfUsbInterfaceGetNumSettings
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetNumSettings"
 - "WdfUsbInterfaceGetNumSettings"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.5
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
- WdfUsbInterfaceGetNumSettings
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetNumSettings function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetNumSettings</b> method returns the number of alternate settings that a specified USB interface supports.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


## -returns



<b>WdfUsbInterfaceGetNumSettings</b> returns the number of alternate settings that the specified USB interface supports.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver can call <b>WdfUsbInterfaceGetNumSettings</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

For more information about the <b>WdfUsbInterfaceGetNumSettings</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of alternate settings that are available for a specified USB interface.

```cpp
BYTE altSettings;

altSettings = WdfUsbInterfaceGetNumSettings(UsbInterface);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>
 

 

