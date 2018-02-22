---
UID: NF:wdfusb.WdfUsbInterfaceGetNumSettings
title: WdfUsbInterfaceGetNumSettings function
author: windows-driver-content
description: The WdfUsbInterfaceGetNumSettings method returns the number of alternate settings that a specified USB interface supports.
old-location: wdf\wdfusbinterfacegetnumsettings.htm
old-project: wdf
ms.assetid: 07de1b64-bafb-4b5b-8ef3-24b87ae0c273
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFUsbRef_5515a8bf-1a43-434c-9806-75393a17fdf5.xml, wdf.wdfusbinterfacegetnumsettings, WdfUsbInterfaceGetNumSettings method, kmdf.wdfusbinterfacegetnumsettings, WdfUsbInterfaceGetNumSettings, wdfusb/WdfUsbInterfaceGetNumSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbInterfaceGetNumSettings
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetNumSettings function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetNumSettings</b> method returns the number of alternate settings that a specified USB interface supports.


## -syntax


````
BYTE WdfUsbInterfaceGetNumSettings(
  _In_ WDFUSBINTERFACE UsbInterface
);
````


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


## -returns



<b>WdfUsbInterfaceGetNumSettings</b> returns the number of alternate settings that the specified USB interface supports.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver can call <b>WdfUsbInterfaceGetNumSettings</b> after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

For more information about the <b>WdfUsbInterfaceGetNumSettings</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of alternate settings that are available for a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE altSettings;

altSettings = WdfUsbInterfaceGetNumSettings(UsbInterface);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetNumSettings method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

