---
UID: NF:wudfusb.IWDFUsbInterface.GetConfiguredSettingIndex
title: IWDFUsbInterface::GetConfiguredSettingIndex (wudfusb.h)
description: The GetConfiguredSettingIndex method retrieves the current setting index for a USB interface.
old-location: wdf\iwdfusbinterface_getconfiguredsettingindex.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbInterface::GetConfiguredSettingIndex"]
ms.keywords: GetConfiguredSettingIndex, GetConfiguredSettingIndex method, GetConfiguredSettingIndex method,IWDFUsbInterface interface, IWDFUsbInterface interface,GetConfiguredSettingIndex method, IWDFUsbInterface.GetConfiguredSettingIndex, IWDFUsbInterface::GetConfiguredSettingIndex, UMDFUSBref_5c2cdbd4-d660-4933-b1fb-a99852b5cba8.xml, umdf.iwdfusbinterface_getconfiguredsettingindex, wdf.iwdfusbinterface_getconfiguredsettingindex, wudfusb/IWDFUsbInterface::GetConfiguredSettingIndex
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
 - IWDFUsbInterface::GetConfiguredSettingIndex
 - wudfusb/IWDFUsbInterface::GetConfiguredSettingIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbInterface.GetConfiguredSettingIndex
---

# IWDFUsbInterface::GetConfiguredSettingIndex


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetConfiguredSettingIndex</b> method retrieves the current setting index for a USB interface.

## -returns

<b>GetConfiguredSettingIndex</b> returns the current setting index for the USB interface.

## -remarks

The <b>GetConfiguredSettingIndex</b> method is provided for convenience because a UMDF driver can obtain the current setting index from the <b>bAlternateSetting</b> member of the <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure that the driver retrieves when it calls the <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">IWDFUsbInterface::GetInterfaceDescriptor</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbinterface">IWDFUsbInterface</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">IWDFUsbInterface::GetInterfaceDescriptor</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>
