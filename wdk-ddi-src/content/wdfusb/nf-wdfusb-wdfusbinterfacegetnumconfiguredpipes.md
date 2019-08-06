---
UID: NF:wdfusb.WdfUsbInterfaceGetNumConfiguredPipes
title: WdfUsbInterfaceGetNumConfiguredPipes function (wdfusb.h)
description: The WdfUsbInterfaceGetNumConfiguredPipes method returns the number of pipes that are configured for a specified USB device interface.
old-location: wdf\wdfusbinterfacegetnumconfiguredpipes.htm
tech.root: wdf
ms.assetid: dbc929a9-696b-42e1-9888-9e8c0b1e01c9
ms.date: 02/26/2018
ms.keywords: DFUsbRef_4273baba-c0e8-4bda-b6da-c9c9f00cabf9.xml, WdfUsbInterfaceGetNumConfiguredPipes, WdfUsbInterfaceGetNumConfiguredPipes method, kmdf.wdfusbinterfacegetnumconfiguredpipes, wdf.wdfusbinterfacegetnumconfiguredpipes, wdfusb/WdfUsbInterfaceGetNumConfiguredPipes
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetNumConfiguredPipes"
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
- WdfUsbInterfaceGetNumConfiguredPipes
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetNumConfiguredPipes function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetNumConfiguredPipes</b> method returns the number of pipes that are configured for a specified USB device interface.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


## -returns



<b>WdfUsbInterfaceGetNumConfiguredPipes</b> returns the number of pipes that are configured for the specified interface.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver can call <b>WdfUsbInterfaceGetNumConfiguredPipes</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>.

For more information about the <b>WdfUsbInterfaceGetNumConfiguredPipes</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of pipes that are configured for a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE pipeCount;

pipeCount = WdfUsbInterfaceGetNumConfiguredPipes(UsbInterface);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>
 

 

