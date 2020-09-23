---
UID: NF:wudfusb.IWDFUsbInterface.GetInterfaceDescriptor
title: IWDFUsbInterface::GetInterfaceDescriptor (wudfusb.h)
description: The GetInterfaceDescriptor method retrieves a descriptor for a USB interface.
old-location: wdf\iwdfusbinterface_getinterfacedescriptor.htm
tech.root: wdf
ms.assetid: ae4cffc8-65db-452c-9b85-19752c32c421
ms.date: 02/26/2018
keywords: ["IWDFUsbInterface::GetInterfaceDescriptor"]
ms.keywords: GetInterfaceDescriptor, GetInterfaceDescriptor method, GetInterfaceDescriptor method,IWDFUsbInterface interface, IWDFUsbInterface interface,GetInterfaceDescriptor method, IWDFUsbInterface.GetInterfaceDescriptor, IWDFUsbInterface::GetInterfaceDescriptor, UMDFUSBref_2d9877fd-47c4-4629-8656-d5d513260b2d.xml, umdf.iwdfusbinterface_getinterfacedescriptor, wdf.iwdfusbinterface_getinterfacedescriptor, wudfusb/IWDFUsbInterface::GetInterfaceDescriptor
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFUsbInterface::GetInterfaceDescriptor
 - wudfusb/IWDFUsbInterface::GetInterfaceDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbInterface.GetInterfaceDescriptor
---

# IWDFUsbInterface::GetInterfaceDescriptor


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInterfaceDescriptor</b> method retrieves a descriptor for a USB interface.

## -parameters

### -param UsbAltInterfaceDescriptor 

[out]
A pointer to a variable that receives the USB interface descriptor.

## -remarks

After a UMDF driver calls the <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">IWDFUsbTargetDevice::RetrieveUsbInterface</a> method to retrieve the first USB interface for the USB device, a UMDF driver should retrieve the descriptor for the USB interface. Therefore, the <b>GetInterfaceDescriptor</b> method does not fail.

For a code example of how to use the <b>GetInterfaceDescriptor</b> method, see <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetfactory-createusbtargetdevice">IWDFUsbTargetFactory::CreateUsbTargetDevice</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">IWDFUsbTargetDevice::RetrieveUsbInterface</a>