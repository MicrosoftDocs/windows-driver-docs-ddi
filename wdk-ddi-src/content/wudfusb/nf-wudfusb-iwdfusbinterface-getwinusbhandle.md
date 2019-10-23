---
UID: NF:wudfusb.IWDFUsbInterface.GetWinUsbHandle
title: IWDFUsbInterface::GetWinUsbHandle (wudfusb.h)
description: The GetWinUsbHandle method retrieves the WinUsb interface handle that is associated with a USB interface.
old-location: wdf\iwdfusbinterface_getwinusbhandle.htm
tech.root: wdf
ms.assetid: 31c23596-21b2-4fb2-96bd-5372fe2432ab
ms.date: 02/26/2018
ms.keywords: GetWinUsbHandle, GetWinUsbHandle method, GetWinUsbHandle method,IWDFUsbInterface interface, IWDFUsbInterface interface,GetWinUsbHandle method, IWDFUsbInterface.GetWinUsbHandle, IWDFUsbInterface::GetWinUsbHandle, UMDFUSBref_6c94f0cc-8995-45c9-8101-bc123b0e48bf.xml, umdf.iwdfusbinterface_getwinusbhandle, wdf.iwdfusbinterface_getwinusbhandle, wudfusb/IWDFUsbInterface::GetWinUsbHandle
ms.topic: method
f1_keywords:
 - "wudfusb/IWDFUsbInterface.GetWinUsbHandle"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUsbInterface.GetWinUsbHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbInterface::GetWinUsbHandle


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWinUsbHandle</b> method retrieves the WinUsb interface handle that is associated with a USB interface.


## -parameters






## -returns



<b>GetWinUsbHandle</b> returns the WinUsb interface handle that is associated with the USB interface.




## -remarks



If called on the default interface, the <b>IWDFUsbInterface::GetWinUsbHandle</b> method returns the same WinUsb interface handle as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle">IWDFUsbTargetDevice::GetWinUsbHandle</a>. The default interface is identified by index zero.

If called on interfaces with index greater than zero, <b>IWDFUsbInterface::GetWinUsbHandle</b> returns a different handle  than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle">IWDFUsbTargetDevice::GetWinUsbHandle</a>.

  A UMDF driver can use the WinUsb interface handle to bypass the UMDF interfaces and call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540046(v=vs.85)">WinUSB Routines</a> directly for interface-related operations.

The UMDF driver should not call the <a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_free">WinUsb_Free</a> function to free the WinUsb interface handle because the USB interface object owns the handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_free">WinUsb_Free</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_initialize">WinUsb_Initialize</a>
 

 

