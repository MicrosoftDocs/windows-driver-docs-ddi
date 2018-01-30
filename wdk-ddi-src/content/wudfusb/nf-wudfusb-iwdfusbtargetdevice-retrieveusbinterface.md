---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrieveUsbInterface
title: IWDFUsbTargetDevice::RetrieveUsbInterface method
author: windows-driver-content
description: The RetrieveUsbInterface method retrieves the specified USB interface for a USB device.
old-location: wdf\iwdfusbtargetdevice_retrieveusbinterface.htm
old-project: wdf
ms.assetid: 9dfa8686-a815-417c-9488-dd86de0e15a2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RetrieveUsbInterface method, IWDFUsbTargetDevice::RetrieveUsbInterface, IWDFUsbTargetDevice interface, RetrieveUsbInterface method, wudfusb/IWDFUsbTargetDevice::RetrieveUsbInterface, UMDFUSBref_cc346a35-4508-40ac-b959-20174a1b39af.xml, RetrieveUsbInterface method, IWDFUsbTargetDevice interface, umdf.iwdfusbtargetdevice_retrieveusbinterface, wdf.iwdfusbtargetdevice_retrieveusbinterface, RetrieveUsbInterface, IWDFUsbTargetDevice
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
-	IWDFUsbTargetDevice.RetrieveUsbInterface
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::RetrieveUsbInterface method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUsbInterface</b> method retrieves the specified USB interface for a USB device.


## -syntax


````
HRESULT RetrieveUsbInterface(
  [in]  UCHAR            InterfaceIndex,
  [out] IWDFUsbInterface **ppUsbInterface
);
````


## -parameters




### -param InterfaceIndex [in]

The index of the interface to retrieve.


### -param ppUsbInterface [out]

A pointer to a variable that receives a pointer to the specified <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interface for the USB device.


## -returns


<b>RetrieveUsbInterface</b> returns one of the following values: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/9dfa8686-a815-417c-9488-dd86de0e15a2">RetrieveUsbInterface</a> successfully retrieved the specified USB interface for the USB device. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/9dfa8686-a815-417c-9488-dd86de0e15a2">RetrieveUsbInterface</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table> 



## -remarks


The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560366">IWDFUsbTargetDevice::GetNumInterfaces</a> method to retrieve the total number of USB interfaces that are available. 

The driver can use the interface pointer that <b>RetrieveUsbInterface</b> retrieves, to call the methods that the <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interface provides. For more information about using these methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-interfaces-in-umdf-1-x-drivers">Working with USB Interfaces in UMDF</a>.



## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>

<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560366">IWDFUsbTargetDevice::GetNumInterfaces</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::RetrieveUsbInterface method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

