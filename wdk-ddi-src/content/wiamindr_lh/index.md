---
UID: NA:wiamindr_lh
ms.assetid: 8bb4455b-7b9a-3281-8f57-256069118040
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wiamindr_Lh.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Wiamindr_Lh.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_MINIDRV_TRANSFER_CONTEXT structure](ns-wiamindr_lh-_minidrv_transfer_context.md) | The MINIDRV_TRANSFER_CONTEXT structure is used to store image and other information needed for a memory-callback data transfer or a file data transfer. |
| [_WIAS_CHANGED_VALUE_INFO structure](ns-wiamindr_lh-_wias_changed_value_info.md) | The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property. |
| [_WIAS_DOWN_SAMPLE_INFO structure](ns-wiamindr_lh-_wias_down_sample_info.md) | The WIAS_DOWN_SAMPLE_INFO structure stores information used by the downsampling helper function, wiasDownSampleBuffer. |
| [_WIAS_ENDORSER_INFO structure](ns-wiamindr_lh-_wias_endorser_info.md) | The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs. |
| [_WIAS_ENDORSER_VALUE structure](ns-wiamindr_lh-_wias_endorser_value.md) | The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings. |
| [_WIA_DEV_CAP_DRV structure](ns-wiamindr_lh-_wia_dev_cap_drv.md) | The WIA_DEV_CAP_DRV structure is used to enumerate device capabilities. A device capability is defined by an event or command that the device supports. |
| [_WIA_PROPERTY_CONTEXT structure](ns-wiamindr_lh-_wia_property_context.md) | The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context. |
| [_WIA_PROPERTY_INFO structure](ns-wiamindr_lh-_wia_property_info.md) | The WIA_PROPERTY_INFO structure is used to store default access and valid value information for an item property of arbitrary type. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWiaDrvItem interface](nn-wiamindr_lh-iwiadrvitem.md) | The IWiaDrvItem interface provides methods that a WIA minidriver can use to manage a tree of IWiaDrvItem items. |
| [IWiaMiniDrv interface](nn-wiamindr_lh-iwiaminidrv.md) | The IWiaMiniDrv interface provides the methods that are the entry points for all communication between the minidriver and the WIA service. These methods allow the WIA service to control the device. |
| [IWiaMiniDrvCallBack interface](nn-wiamindr_lh-iwiaminidrvcallback.md) | The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service. |
| [IWiaMiniDrvTransferCallback interface](nn-wiamindr_lh-iwiaminidrvtransfercallback.md) | This is a Callback interface that is called by the WIA mini-driver for stream-based transfers. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWiaDrvItem::AddItemToFolder method](nf-wiamindr_lh-iwiadrvitem-additemtofolder.md) | The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree. |
| [IWiaDrvItem::DumpItemData method](nf-wiamindr_lh-iwiadrvitem-dumpitemdata.md) | The IWiaDrvItem |
| [IWiaDrvItem::FindChildItemByName method](nf-wiamindr_lh-iwiadrvitem-findchilditembyname.md) | The IWiaDrvItem |
| [IWiaDrvItem::FindItemByName method](nf-wiamindr_lh-iwiadrvitem-finditembyname.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetDeviceSpecContext method](nf-wiamindr_lh-iwiadrvitem-getdevicespeccontext.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetFirstChildItem method](nf-wiamindr_lh-iwiadrvitem-getfirstchilditem.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetFullItemName method](nf-wiamindr_lh-iwiadrvitem-getfullitemname.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetItemFlags method](nf-wiamindr_lh-iwiadrvitem-getitemflags.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetItemName method](nf-wiamindr_lh-iwiadrvitem-getitemname.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetNextSiblingItem method](nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem.md) | The IWiaDrvItem |
| [IWiaDrvItem::GetParentItem method](nf-wiamindr_lh-iwiadrvitem-getparentitem.md) | The IWiaDrvItem |
| [IWiaDrvItem::RemoveItemFromFolder method](nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder.md) | The IWiaDrvItem |
| [IWiaDrvItem::UnlinkItemTree method](nf-wiamindr_lh-iwiadrvitem-unlinkitemtree.md) | The IWiaDrvItem |
| [IWiaMiniDrv::drvAcquireItemData method](nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvAnalyzeItem method](nf-wiamindr_lh-iwiaminidrv-drvanalyzeitem.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvDeleteItem method](nf-wiamindr_lh-iwiaminidrv-drvdeleteitem.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvDeviceCommand method](nf-wiamindr_lh-iwiaminidrv-drvdevicecommand.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvFreeDrvItemContext method](nf-wiamindr_lh-iwiaminidrv-drvfreedrvitemcontext.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvGetCapabilities method](nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvGetDeviceErrorStr method](nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvGetWiaFormatInfo method](nf-wiamindr_lh-iwiaminidrv-drvgetwiaformatinfo.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvInitItemProperties method](nf-wiamindr_lh-iwiaminidrv-drvinititemproperties.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvInitializeWia method](nf-wiamindr_lh-iwiaminidrv-drvinitializewia.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvLockWiaDevice method](nf-wiamindr_lh-iwiaminidrv-drvlockwiadevice.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvNotifyPnpEvent method](nf-wiamindr_lh-iwiaminidrv-drvnotifypnpevent.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvReadItemProperties method](nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvUnInitializeWia method](nf-wiamindr_lh-iwiaminidrv-drvuninitializewia.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvUnLockWiaDevice method](nf-wiamindr_lh-iwiaminidrv-drvunlockwiadevice.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvValidateItemProperties method](nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties.md) | The IWiaMiniDrv |
| [IWiaMiniDrv::drvWriteItemProperties method](nf-wiamindr_lh-iwiaminidrv-drvwriteitemproperties.md) | The IWiaMiniDrv |
| [IWiaMiniDrvCallBack::MiniDrvCallback method](nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback.md) | The MiniDrvCallback method provides a callback method for WIA minidrivers to use during a callback data transfer. |
| [IWiaMiniDrvTransferCallback::GetNextStream method](nf-wiamindr_lh-iwiaminidrvtransfercallback-getnextstream.md) | Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload). |
| [IWiaMiniDrvTransferCallback::SendMessage method](nf-wiamindr_lh-iwiaminidrvtransfercallback-sendmessage.md) | Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer. |
