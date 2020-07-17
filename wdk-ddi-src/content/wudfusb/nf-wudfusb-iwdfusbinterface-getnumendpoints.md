---
UID: NF:wudfusb.IWDFUsbInterface.GetNumEndPoints
title: IWDFUsbInterface::GetNumEndPoints (wudfusb.h)
description: The GetNumEndPoints method retrieves the number of endpoints (pipes) on a USB interface.
old-location: wdf\iwdfusbinterface_getnumendpoints.htm
tech.root: wdf
ms.assetid: 60ec8b38-8ab2-45d8-92ab-5943fd9bba79
ms.date: 02/26/2018
keywords: ["IWDFUsbInterface::GetNumEndPoints"]
ms.keywords: GetNumEndPoints, GetNumEndPoints method, GetNumEndPoints method,IWDFUsbInterface interface, IWDFUsbInterface interface,GetNumEndPoints method, IWDFUsbInterface.GetNumEndPoints, IWDFUsbInterface::GetNumEndPoints, UMDFUSBref_ae1352c4-217e-49fd-9275-6c80103af753.xml, umdf.iwdfusbinterface_getnumendpoints, wdf.iwdfusbinterface_getnumendpoints, wudfusb/IWDFUsbInterface::GetNumEndPoints
f1_keywords:
 - "wudfusb/IWDFUsbInterface.GetNumEndPoints"
 - "IWDFUsbInterface.GetNumEndPoints"
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
- IWDFUsbInterface.GetNumEndPoints
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbInterface::GetNumEndPoints


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumEndPoints</b> method retrieves the number of endpoints (pipes) on a USB interface.


## -returns



<b>GetNumEndPoints</b> returns the number of endpoints on the USB interface.




## -remarks



The <b>GetNumEndPoints</b> method is provided for convenience because a UMDF driver can obtain the number of endpoints from the <b>bNumEndpoints</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure that the driver retrieves when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">IWDFUsbInterface::GetInterfaceDescriptor</a> method. 


#### Examples

The following code example retrieves the number of pipes on a USB interface and then retrieves particular types of pipes.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> HRESULT  hr;
 UCHAR  NumEndPoints;
 NumEndPoints = pIUsbInterface->GetNumEndPoints();

 if (NumEndPoints != NUM_OSRUSB_ENDPOINTS) {
     hr = E_UNEXPECTED;
 }
 if (SUCCEEDED(hr))  {
     for (UCHAR PipeIndex = 0; PipeIndex < NumEndPoints; PipeIndex++) {
     hr = pIUsbInterface->RetrieveUsbPipeObject(PipeIndex, 
                                                &pIUsbPipe);
     if (FAILED(hr)) {
        // Output an error.
     }
     else {
         if ( pIUsbPipe->IsInEndPoint() && (UsbdPipeTypeBulk == pIUsbPipe->GetType()) ) {
             pIUsbInputPipe = pIUsbPipe;
         }
         else if ( pIUsbPipe->IsOutEndPoint() && (UsbdPipeTypeBulk == pIUsbPipe->GetType()) )
         {
              pIUsbOutputPipe = pIUsbPipe;
         }
         else
              {
                  SAFE_RELEASE(pIUsbPipe);
              }
          }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">IWDFUsbInterface::GetInterfaceDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>
 

 

