---
UID: NF:wdfusb.WdfUsbInterfaceGetNumEndpoints
title: WdfUsbInterfaceGetNumEndpoints function
author: windows-driver-content
description: The WdfUsbInterfaceGetNumEndpoints method returns the number of endpoints that are associated with a specified alternate setting of a specified USB interface.
old-location: wdf\wdfusbinterfacegetnumendpoints.htm
old-project: wdf
ms.assetid: 6041b96e-2364-4592-9bc5-de4fb1b36957
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfusbinterfacegetnumendpoints, PFN_WDFUSBINTERFACEGETNUMENDPOINTS, wdfusb/WdfUsbInterfaceGetNumEndpoints, WdfUsbInterfaceGetNumEndpoints method, wdf.wdfusbinterfacegetnumendpoints, WdfUsbInterfaceGetNumEndpoints, DFUsbRef_e0c08e93-b09f-40d0-9958-e4e51d7b887d.xml
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
-	WdfUsbInterfaceGetNumEndpoints
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetNumEndpoints function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetNumEndpoints</b> method returns the number of endpoints that are associated with a specified alternate setting of a specified USB interface.


## -syntax


````
BYTE WdfUsbInterfaceGetNumEndpoints(
  _In_ WDFUSBINTERFACE UsbInterface,
  _In_ UCHAR           SettingIndex
);
````


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. For more information about alternate settings, see the USB specification.


## -returns


If the specified index is valid, <b>WdfUsbInterfaceGetNumEndpoints</b> returns the number of endpoints that are associated with the specified interface's alternate setting. Otherwise, the method returns zero.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about the <b>WdfUsbInterfaceGetNumEndpoints</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetNumEndpoints method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

