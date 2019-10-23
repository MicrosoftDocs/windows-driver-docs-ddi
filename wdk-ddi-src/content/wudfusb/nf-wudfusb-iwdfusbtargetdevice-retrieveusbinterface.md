---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrieveUsbInterface
title: IWDFUsbTargetDevice::RetrieveUsbInterface (wudfusb.h)
description: The RetrieveUsbInterface method retrieves the specified USB interface for a USB device.
old-location: wdf\iwdfusbtargetdevice_retrieveusbinterface.htm
tech.root: wdf
ms.assetid: 9dfa8686-a815-417c-9488-dd86de0e15a2
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetDevice interface,RetrieveUsbInterface method, IWDFUsbTargetDevice.RetrieveUsbInterface, IWDFUsbTargetDevice::RetrieveUsbInterface, RetrieveUsbInterface, RetrieveUsbInterface method, RetrieveUsbInterface method,IWDFUsbTargetDevice interface, UMDFUSBref_cc346a35-4508-40ac-b959-20174a1b39af.xml, umdf.iwdfusbtargetdevice_retrieveusbinterface, wdf.iwdfusbtargetdevice_retrieveusbinterface, wudfusb/IWDFUsbTargetDevice::RetrieveUsbInterface
ms.topic: method
f1_keywords:
 - "wudfusb/IWDFUsbTargetDevice.RetrieveUsbInterface"
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
- IWDFUsbTargetDevice.RetrieveUsbInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice::RetrieveUsbInterface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUsbInterface</b> method retrieves the specified USB interface for a USB device.


## -parameters




### -param InterfaceIndex [in]

The index of the interface to retrieve.


### -param ppUsbInterface [out]

A pointer to a variable that receives a pointer to the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a> interface for the USB device.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">RetrieveUsbInterface</a> successfully retrieved the specified USB interface for the USB device. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">RetrieveUsbInterface</a> encountered an allocation failure.

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



The driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getnuminterfaces">IWDFUsbTargetDevice::GetNumInterfaces</a> method to retrieve the total number of USB interfaces that are available. 

The driver can use the interface pointer that <b>RetrieveUsbInterface</b> retrieves, to call the methods that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a> interface provides. For more information about using these methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-interfaces-in-umdf-1-x-drivers">Working with USB Interfaces in UMDF</a>.


#### Examples

For a code example of how to use the <b>RetrieveUsbInterface</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetfactory-createusbtargetdevice">IWDFUsbTargetFactory::CreateUsbTargetDevice</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getnuminterfaces">IWDFUsbTargetDevice::GetNumInterfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a>
 

 

