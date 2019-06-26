---
UID: NN:wiamindr_lh.IWiaMiniDrv
title: IWiaMiniDrv (wiamindr_lh.h)
description: The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.
old-location: image\iwiaminidrv_interface.htm
tech.root: image
ms.assetid: 15068d10-5e24-427c-9684-24ce67b75ada
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], IWiaMiniDrv interface [Imaging Devices],described, MiniDrv_8a22bfee-13f8-4efc-b31d-8dd9fabfe131.xml, image.iwiaminidrv_interface, wiamindr_lh/IWiaMiniDrv
ms.topic: interface
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaMiniDrv
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv interface


## -description


The <b>IWiaMiniDrv</b> interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.

A WIA minidriver writer must implement each method in this interface, although the implementations are not required to do anything more than return E_NOTIMPL (for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem">IWiaMiniDrv::drvAnalyzeItem</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>) or S_OK (for the other methods in this interface).


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaMiniDrv</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaMiniDrv</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaMiniDrv</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata">drvAcquireItemData</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvAcquireItemData</b> method is called by the WIA service to transfer data from the device to an application.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem">drvAnalyzeItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvAnalyzeItem</b> method inspects an item, and creates subitems, if necessary.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvdeleteitem">drvDeleteItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvDeleteItem</b> method deletes the current driver item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvdevicecommand">drvDeviceCommand</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvDeviceCommand</b> method issues a command to a WIA device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext">drvFreeDrvItemContext</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities">drvGetCapabilities</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetCapabilities</b> method returns an array of events and commands that a device supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">drvGetDeviceErrorStr</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetDeviceErrorStr </b>method maps an error code to a Unicode string that describes the error.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetwiaformatinfo">drvGetWiaFormatInfo</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetWiaFormatInfo</b> method finds the image formats and media types that the WIA hardware device supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinitializewia">drvInitializeWia</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvInitializeWia</b> method initializes the minidriver and builds the driver item tree representing the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinititemproperties">drvInitItemProperties</a>
</td>
<td align="left" width="63%">
The<b> IWiaMiniDrv::drvInitItemProperties</b> method initializes WIA driver item properties for each item in an application item tree.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvlockwiadevice">drvLockWiaDevice</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvLockWiaDevice</b> method locks the WIA hardware device so that only the current minidriver can access it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvnotifypnpevent">drvNotifyPnpEvent</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvNotifyPnpEvent</b> method responds to the event received from the WIA service.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties">drvReadItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvuninitializewia">drvUnInitializeWia</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvUnInitializeWia</b> method releases resources held by the minidriver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvunlockwiadevice">drvUnLockWiaDevice</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvUnLockWiaDevice</b> method unlocks the WIA hardware device so that any minidriver can access it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties">drvValidateItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvValidateItemProperties</b> method validates an item's properties against the set of valid values for each property and will update those properties if necessary.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties">drvWriteItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvWriteItemProperties</b> method writes driver item properties to a WIA hardware device.

</td>
</tr>
</table> 

