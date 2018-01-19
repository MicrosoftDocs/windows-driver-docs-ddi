---
UID: NF:wiamindr_lh.IWiaDrvItem.RemoveItemFromFolder
title: IWiaDrvItem::RemoveItemFromFolder method
author: windows-driver-content
description: The IWiaDrvItem::RemoveItemFromFolder method removes an item from a parent folder.
old-location: image\iwiadrvitem_removeitemfromfolder.htm
old-project: image
ms.assetid: f800427e-d6b6-4f4c-aee7-4b2b0d0aa0c4
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaDrvItem, IWiaDrvItem::RemoveItemFromFolder, RemoveItemFromFolder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaDrvItem.RemoveItemFromFolder
req.alt-loc: wiamindr_lh.h
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
req.typenames: *PSCANWINDOW, SCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem::RemoveItemFromFolder method



## -description
The <b>IWiaDrvItem::RemoveItemFromFolder</b> method removes an item from a parent folder.



## -syntax

````
HRESULT RemoveItemFromFolder(
  [in] LONG lReason
);
````


## -parameters

### -param lReason [in]

Specifies the reason for the removal of the item from the folder. This parameter can be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WiaItemTypeDeleted 

</td>
<td>
The item is marked as deleted.

</td>
</tr>
<tr>
<td>
WiaItemTypeDisconnected

</td>
<td>
The item is a disconnected device.

</td>
</tr>
</table>
 


## -returns
If the method succeeds, it returns S_OK. If the item to be removed is a folder and the folder is not empty, the method returns E_INVALIDARG. If <i>lReason</i> contains an invalid reason, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.


## -remarks
After the item has been removed from the folder, it can no longer be used for device access.


## -see-also
<dl>
<dt>
<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543856">IWiaDrvItem::AddItemToFolder</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::RemoveItemFromFolder method%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

