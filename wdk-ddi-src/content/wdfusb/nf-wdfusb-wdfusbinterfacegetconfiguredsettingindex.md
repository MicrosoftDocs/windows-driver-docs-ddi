---
UID: NF:wdfusb.WdfUsbInterfaceGetConfiguredSettingIndex
title: WdfUsbInterfaceGetConfiguredSettingIndex function
author: windows-driver-content
description: The WdfUsbInterfaceGetConfiguredSettingIndex method returns the alternate setting index that is currently selected for a specified USB device interface.
old-location: wdf\wdfusbinterfacegetconfiguredsettingindex.htm
old-project: wdf
ms.assetid: ca8f1fae-1655-4e0d-baa4-133f11cf246f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WdfUsbInterfaceGetConfiguredSettingIndex, WdfUsbInterfaceGetConfiguredSettingIndex method, kmdf.wdfusbinterfacegetconfiguredsettingindex, WdfUsbInterfaceGetConfiguredSettingIndex, PFN_WDFUSBINTERFACEGETCONFIGUREDSETTINGINDEX, wdf.wdfusbinterfacegetconfiguredsettingindex, DFUsbRef_720a2078-a35c-491b-a8d1-7a2b3d5c88f1.xml
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
-	WdfUsbInterfaceGetConfiguredSettingIndex
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetConfiguredSettingIndex function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> method returns the alternate setting index that is currently selected for a specified USB device interface.


## -syntax


````
BYTE WdfUsbInterfaceGetConfiguredSettingIndex(
  _In_ WDFUSBINTERFACE Interface
);
````


## -parameters




### -param Interface [in]

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>. 


## -returns


If the operation succeeds, <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> returns the alternate setting index that is currently selected for the specified interface. If the interface is not configured, the method returns zero.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about the <b>WdfUsbInterfaceGetConfiguredSettingIndex</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetConfiguredSettingIndex method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

