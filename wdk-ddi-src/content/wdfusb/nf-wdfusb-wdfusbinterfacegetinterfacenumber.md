---
UID: NF:wdfusb.WdfUsbInterfaceGetInterfaceNumber
title: WdfUsbInterfaceGetInterfaceNumber function (wdfusb.h)
description: The WdfUsbInterfaceGetInterfaceNumber method returns the interface number of a specified USB interface object.
old-location: wdf\wdfusbinterfacegetinterfacenumber.htm
tech.root: wdf
ms.assetid: bc39e3ae-6899-423d-be1d-b3322efface8
ms.date: 02/26/2018
ms.keywords: DFUsbRef_035fbae3-67d4-4df6-8718-30851a0d60ca.xml, WdfUsbInterfaceGetInterfaceNumber, WdfUsbInterfaceGetInterfaceNumber method, kmdf.wdfusbinterfacegetinterfacenumber, wdf.wdfusbinterfacegetinterfacenumber, wdfusb/WdfUsbInterfaceGetInterfaceNumber
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetInterfaceNumber"
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
- WdfUsbInterfaceGetInterfaceNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetInterfaceNumber function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetInterfaceNumber</b> method returns the interface number of a specified USB interface object.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


## -returns



<b>WdfUsbInterfaceGetInterfaceNumber</b> returns the interface number. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about interface numbers, see the USB specification.

For more information about the <b>WdfUsbInterfaceGetInterfaceNumber</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the interface number of a specified USB interface object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE interfaceNumber; 

interfaceNumber = WdfUsbInterfaceGetInterfaceNumber(UsbInterface);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
 

 

