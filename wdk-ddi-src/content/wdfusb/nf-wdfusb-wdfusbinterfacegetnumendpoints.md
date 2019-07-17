---
UID: NF:wdfusb.WdfUsbInterfaceGetNumEndpoints
title: WdfUsbInterfaceGetNumEndpoints function (wdfusb.h)
description: The WdfUsbInterfaceGetNumEndpoints method returns the number of endpoints that are associated with a specified alternate setting of a specified USB interface.
old-location: wdf\wdfusbinterfacegetnumendpoints.htm
tech.root: wdf
ms.assetid: 6041b96e-2364-4592-9bc5-de4fb1b36957
ms.date: 02/26/2018
ms.keywords: DFUsbRef_e0c08e93-b09f-40d0-9958-e4e51d7b887d.xml, WdfUsbInterfaceGetNumEndpoints, WdfUsbInterfaceGetNumEndpoints method, kmdf.wdfusbinterfacegetnumendpoints, wdf.wdfusbinterfacegetnumendpoints, wdfusb/WdfUsbInterfaceGetNumEndpoints
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetNumEndpoints"
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
req.irql: "<=DISPATCH_LEVEL"
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
- WdfUsbInterfaceGetNumEndpoints
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetNumEndpoints function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetNumEndpoints</b> method returns the number of endpoints that are associated with a specified alternate setting of a specified USB interface.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


## -returns



If the specified index is valid, <b>WdfUsbInterfaceGetNumEndpoints</b> returns the number of endpoints that are associated with the specified interface's alternate setting. Otherwise, the method returns zero.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbInterfaceGetNumEndpoints</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of endpoints for alternate setting 0 of a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE  numEndpoints;
numEndpoints = WdfUsbInterfaceGetNumEndpoints(
                                              UsbInterface,
                                              0
                                              );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
 

 

