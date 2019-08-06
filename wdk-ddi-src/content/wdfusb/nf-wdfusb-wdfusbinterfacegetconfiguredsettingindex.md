---
UID: NF:wdfusb.WdfUsbInterfaceGetConfiguredSettingIndex
title: WdfUsbInterfaceGetConfiguredSettingIndex function (wdfusb.h)
description: The WdfUsbInterfaceGetConfiguredSettingIndex method returns the alternate setting index that is currently selected for a specified USB device interface.
old-location: wdf\wdfusbinterfacegetconfiguredsettingindex.htm
tech.root: wdf
ms.assetid: ca8f1fae-1655-4e0d-baa4-133f11cf246f
ms.date: 02/26/2018
ms.keywords: DFUsbRef_720a2078-a35c-491b-a8d1-7a2b3d5c88f1.xml, WdfUsbInterfaceGetConfiguredSettingIndex, WdfUsbInterfaceGetConfiguredSettingIndex method, kmdf.wdfusbinterfacegetconfiguredsettingindex, wdf.wdfusbinterfacegetconfiguredsettingindex, wdfusb/WdfUsbInterfaceGetConfiguredSettingIndex
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbInterfaceGetConfiguredSettingIndex"
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
- WdfUsbInterfaceGetConfiguredSettingIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceGetConfiguredSettingIndex function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> method returns the alternate setting index that is currently selected for a specified USB device interface.


## -parameters




### -param Interface [in]

A handle to a USB interface object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 


## -returns



If the operation succeeds, <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> returns the alternate setting index that is currently selected for the specified interface. If the interface is not configured, the method returns zero.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the index for the currently selected alternate setting of a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE settingIndex;

settingIndex = WdfUsbInterfaceGetConfiguredSettingIndex(UsbInterface);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
 

 

