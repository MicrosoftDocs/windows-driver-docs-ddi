---
UID: NF:wudfusb.IWDFUsbTargetDevice.GetWinUsbHandle
title: IWDFUsbTargetDevice::GetWinUsbHandle method
author: windows-driver-content
description: The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a I/O target device object.
old-location: wdf\iwdfusbtargetdevice_getwinusbhandle.htm
old-project: wdf
ms.assetid: 458cbe27-be75-49f4-9849-969d881e0cd2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.iwdfusbtargetdevice_getwinusbhandle, IWDFUsbTargetDevice, umdf.iwdfusbtargetdevice_getwinusbhandle, GetWinUsbHandle, UMDFUSBref_7568c92e-e43d-4013-ab7c-1f4834cd5c14.xml, GetWinUsbHandle method, IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface, GetWinUsbHandle method, GetWinUsbHandle method, wudfusb/IWDFUsbTargetDevice::GetWinUsbHandle, IWDFUsbTargetDevice::GetWinUsbHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUsbTargetDevice.GetWinUsbHandle
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::GetWinUsbHandle method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWinUsbHandle</b> method retrieves the WinUsb interface handle that is associated with a I/O target device object.


## -syntax


````
WINUSB_INTERFACE_HANDLE GetWinUsbHandle();
````


## -parameters






## -returns



<b>GetWinUsbHandle</b> returns the WinUsb interface handle that is associated with the I/O target device object.




## -remarks



<b>IWDFUsbTargetDevice::GetWinUsbHandle</b> returns a WinUsb interface handle to the default interface. The default interface is identified by index zero.

 A UMDF driver can use the WinUsb interface handle to bypass the UMDF interfaces and call <a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">WinUSB Routines</a> directly for certain operations.

The UMDF driver should not call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a> function to free the WinUsb interface handle because the I/O target device object owns the handle.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540277">WinUsb_Initialize</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::GetWinUsbHandle method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

