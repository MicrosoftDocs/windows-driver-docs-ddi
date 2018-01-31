---
UID: NN:wiamindr_lh.IWiaMiniDrv
title: IWiaMiniDrv
author: windows-driver-content
description: The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.
old-location: image\iwiaminidrv_interface.htm
old-project: image
ms.assetid: 15068d10-5e24-427c-9684-24ce67b75ada
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.iwiaminidrv_interface, IWiaMiniDrv interface [Imaging Devices], IWiaMiniDrv interface [Imaging Devices], described, IWiaMiniDrv, wiamindr_lh/IWiaMiniDrv, MiniDrv_8a22bfee-13f8-4efc-b31d-8dd9fabfe131.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wiamindr_lh.h
apiname:
-	IWiaMiniDrv
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrv interface


## -description


The <b>IWiaMiniDrv</b> interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device.

A WIA minidriver writer must implement each method in this interface, although the implementations are not required to do anything more than return E_NOTIMPL (for <a href="https://msdn.microsoft.com/library/windows/hardware/ff543958">IWiaMiniDrv::drvAnalyzeItem</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>) or S_OK (for the other methods in this interface).


## -members

The <b>IWiaMiniDrv</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ab49643b-ab77-49ea-9a3b-e3a184cd29d0">drvAcquireItemData</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvAcquireItemData</b> method is called by the WIA service to transfer data from the device to an application.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e742f898-e663-431d-870e-bb0fe7e89b5a">drvAnalyzeItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvAnalyzeItem</b> method inspects an item, and creates subitems, if necessary.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/616a0edd-d769-411d-bc94-57ba18a00c4d">drvDeleteItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvDeleteItem</b> method deletes the current driver item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e17c81a6-8c4e-41f0-bd98-f7a9a0f20893">drvDeviceCommand</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvDeviceCommand</b> method issues a command to a WIA device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/bc4f751f-d92a-47e6-8cbe-0a587292b160">drvFreeDrvItemContext</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/946a6ea7-5818-4959-adf2-3568c1b64b1a">drvGetCapabilities</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetCapabilities</b> method returns an array of events and commands that a device supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c34a6834-8875-400c-9634-6c2b9b68164f">drvGetDeviceErrorStr</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetDeviceErrorStr </b>method maps an error code to a Unicode string that describes the error.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/f0b7d982-735f-489c-b9f8-81a287f6722a">drvGetWiaFormatInfo</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvGetWiaFormatInfo</b> method finds the image formats and media types that the WIA hardware device supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/93b155eb-0254-441f-b01f-3da8eb7376a5">drvInitializeWia</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvInitializeWia</b> method initializes the minidriver and builds the driver item tree representing the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/06dce5c0-f893-47c7-bee9-1b7f61137ba0">drvInitItemProperties</a>
</td>
<td align="left" width="63%">
The<b> IWiaMiniDrv::drvInitItemProperties</b> method initializes WIA driver item properties for each item in an application item tree.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/674e0a65-1763-41b0-896b-2ef9debc32a5">drvLockWiaDevice</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvLockWiaDevice</b> method locks the WIA hardware device so that only the current minidriver can access it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/55d6d93b-c20f-435b-ba99-2df26bd17240">drvNotifyPnpEvent</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvNotifyPnpEvent</b> method responds to the event received from the WIA service.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/015c2e02-62aa-4037-9974-c8e4b8784fe5">drvReadItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/974de3b5-c129-42ee-a522-071c26726cf1">drvUnInitializeWia</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvUnInitializeWia</b> method releases resources held by the minidriver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/134d224a-d472-4d74-be3e-069dbb46a65c">drvUnLockWiaDevice</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvUnLockWiaDevice</b> method unlocks the WIA hardware device so that any minidriver can access it.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/12052128-9ea7-41cd-bb75-be7175e26c12">drvValidateItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvValidateItemProperties</b> method validates an item's properties against the set of valid values for each property and will update those properties if necessary.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/350cb7f6-499f-4fbc-b5c0-6f4daf2a2af0">drvWriteItemProperties</a>
</td>
<td align="left" width="63%">
The <b>IWiaMiniDrv::drvWriteItemProperties</b> method writes driver item properties to a WIA hardware device.

</td>
</tr>
</table>The <b>IWiaMiniDrv::drvAcquireItemData</b> method is called by the WIA service to transfer data from the device to an application.

The <b>IWiaMiniDrv::drvAnalyzeItem</b> method inspects an item, and creates subitems, if necessary.

The <b>IWiaMiniDrv::drvDeleteItem</b> method deletes the current driver item.

The <b>IWiaMiniDrv::drvDeviceCommand</b> method issues a command to a WIA device.

The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.

The <b>IWiaMiniDrv::drvGetCapabilities</b> method returns an array of events and commands that a device supports.

The <b>IWiaMiniDrv::drvGetDeviceErrorStr </b>method maps an error code to a Unicode string that describes the error.

The <b>IWiaMiniDrv::drvGetWiaFormatInfo</b> method finds the image formats and media types that the WIA hardware device supports.

The <b>IWiaMiniDrv::drvInitializeWia</b> method initializes the minidriver and builds the driver item tree representing the device.

The<b> IWiaMiniDrv::drvInitItemProperties</b> method initializes WIA driver item properties for each item in an application item tree.

The <b>IWiaMiniDrv::drvLockWiaDevice</b> method locks the WIA hardware device so that only the current minidriver can access it.

The <b>IWiaMiniDrv::drvNotifyPnpEvent</b> method responds to the event received from the WIA service.

The <b>IWiaMiniDrv::drvReadItemProperties</b> method reads the driver item properties that need to be updated.

The <b>IWiaMiniDrv::drvUnInitializeWia</b> method releases resources held by the minidriver.

The <b>IWiaMiniDrv::drvUnLockWiaDevice</b> method unlocks the WIA hardware device so that any minidriver can access it.

The <b>IWiaMiniDrv::drvValidateItemProperties</b> method validates an item's properties against the set of valid values for each property and will update those properties if necessary.

The <b>IWiaMiniDrv::drvWriteItemProperties</b> method writes driver item properties to a WIA hardware device.

 

