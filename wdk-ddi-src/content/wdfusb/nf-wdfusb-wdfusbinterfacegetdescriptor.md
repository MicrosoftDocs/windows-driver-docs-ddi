---
UID: NF:wdfusb.WdfUsbInterfaceGetDescriptor
title: WdfUsbInterfaceGetDescriptor function
author: windows-driver-content
description: The WdfUsbInterfaceGetDescriptor method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.
old-location: wdf\wdfusbinterfacegetdescriptor.htm
old-project: wdf
ms.assetid: 70156bfa-8271-42f6-9a22-0d0b77e63b66
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, DFUsbRef_eb98efa1-720d-408c-824f-59cfef80bbba.xml, G, I, U, W, WdfUsbInterfaceGetDescriptor, WdfUsbInterfaceGetDescriptor method, a, b, c, d, e, f, i, kmdf.wdfusbinterfacegetdescriptor, n, o, p, r, s, t, wdf.wdfusbinterfacegetdescriptor, wdfusb/WdfUsbInterfaceGetDescriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfUsbInterfaceGetDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetDescriptor</b> method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface.


## -syntax


````
VOID WdfUsbInterfaceGetDescriptor(
  _In_  WDFUSBINTERFACE           UsbInterface,
  _In_  UCHAR                     SettingIndex,
  _Out_ PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor
);
````


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


### -param InterfaceDescriptor [out]

A pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that the framework fills in.


## -returns



None. 

If the <i>SettingIndex</i> value is invalid, the <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure can receive invalid data. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbInterfaceGetDescriptor</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the alternate setting index for a specified USB interface. Then, the example obtains the USB interface descriptor that represents the USB interface's current alternate setting.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE  settingIndex;
USB_INTERFACE_DESCRIPTOR  interfaceDescriptor;

settingIndex = WdfUsbInterfaceGetConfiguredSettingIndex(
                             UsbInterface
                             );

WdfUsbInterfaceGetDescriptor(
                             UsbInterface,
                             settingIndex,
                             &amp;interfaceDescriptor
                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>



<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetDescriptor method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

