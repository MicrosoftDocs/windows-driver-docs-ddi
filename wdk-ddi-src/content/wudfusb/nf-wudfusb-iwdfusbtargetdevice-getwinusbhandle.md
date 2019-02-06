---
UID: NF:wudfusb.IWDFUsbTargetDevice.GetWinUsbHandle
title: IWDFUsbTargetDevice::GetWinUsbHandle (wudfusb.h)
description: The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a I/O target device object.
old-location: wdf\iwdfusbtargetdevice_getwinusbhandle.htm
tech.root: wdf
ms.assetid: 458cbe27-be75-49f4-9849-969d881e0cd2
ms.date: 02/26/2018
ms.keywords: GetWinUsbHandle, GetWinUsbHandle method, GetWinUsbHandle method,IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface,GetWinUsbHandle method, IWDFUsbTargetDevice.GetWinUsbHandle, IWDFUsbTargetDevice::GetWinUsbHandle, UMDFUSBref_7568c92e-e43d-4013-ab7c-1f4834cd5c14.xml, umdf.iwdfusbtargetdevice_getwinusbhandle, wdf.iwdfusbtargetdevice_getwinusbhandle, wudfusb/IWDFUsbTargetDevice::GetWinUsbHandle
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetDevice.GetWinUsbHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice::GetWinUsbHandle


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWinUsbHandle</b> method retrieves the WinUsb interface handle that is associated with a I/O target device object.


## -parameters






## -returns



<b>GetWinUsbHandle</b> returns the WinUsb interface handle that is associated with the I/O target device object.




## -remarks



<b>IWDFUsbTargetDevice::GetWinUsbHandle</b> returns a WinUsb interface handle to the default interface. The default interface is identified by index zero.

 A UMDF driver can use the WinUsb interface handle to bypass the UMDF interfaces and call <a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">WinUSB Routines</a> directly for certain operations.

The UMDF driver should not call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a> function to free the WinUsb interface handle because the I/O target device object owns the handle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560362">IWDFUsbTargetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540233">WinUsb_Free</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540277">WinUsb_Initialize</a>
 

 

