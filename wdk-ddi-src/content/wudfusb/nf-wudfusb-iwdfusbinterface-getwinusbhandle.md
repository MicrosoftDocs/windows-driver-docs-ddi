---
UID: NF:wudfusb.IWDFUsbInterface.GetWinUsbHandle
title: IWDFUsbInterface::GetWinUsbHandle method
author: windows-driver-content
description: The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a USB interface.
old-location: wdf\iwdfusbinterface_getwinusbhandle.htm
old-project: wdf
ms.assetid: 31c23596-21b2-4fb2-96bd-5372fe2432ab
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetWinUsbHandle method, IWDFUsbInterface interface, GetWinUsbHandle, GetWinUsbHandle method, umdf.iwdfusbinterface_getwinusbhandle, UMDFUSBref_6c94f0cc-8995-45c9-8101-bc123b0e48bf.xml, IWDFUsbInterface::GetWinUsbHandle, wudfusb/IWDFUsbInterface::GetWinUsbHandle, wdf.iwdfusbinterface_getwinusbhandle, IWDFUsbInterface interface, GetWinUsbHandle method, IWDFUsbInterface
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
-	IWDFUsbInterface.GetWinUsbHandle
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# IWDFUsbInterface::GetWinUsbHandle method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWinUsbHandle</b> method retrieves the WinUsb interface handle that is associated with a USB interface.


## -syntax


````
WINUSB_INTERFACE_HANDLE GetWinUsbHandle();
````


## -parameters






## -returns



<b>GetWinUsbHandle</b> returns the WinUsb interface handle that is associated with the USB interface.




## -remarks



If called on the default interface, the <b>IWDFUsbInterface::GetWinUsbHandle</b> method returns the same WinUsb interface handle as <a href="https://msdn.microsoft.com/library/windows/hardware/ff560369">IWDFUsbTargetDevice::GetWinUsbHandle</a>. The default interface is identified by index zero.

If called on interfaces with index greater than zero, <b>IWDFUsbInterface::GetWinUsbHandle</b> returns a different handle  than <a href="https://msdn.microsoft.com/library/windows/hardware/ff560369">IWDFUsbTargetDevice::GetWinUsbHandle</a>.

  A UMDF driver can use the WinUsb interface handle to bypass the UMDF interfaces and call <a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">WinUSB Routines</a> directly for interface-related operations.

The UMDF driver should not call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a> function to free the WinUsb interface handle because the USB interface object owns the handle.




## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540277">WinUsb_Initialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetWinUsbHandle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

