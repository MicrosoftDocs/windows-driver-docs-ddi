---
UID: NS:wiadevd.tagDEVICEDIALOGDATA
title: tagDEVICEDIALOGDATA
author: windows-driver-content
description: The DEVICEDIALOGDATA structure contains all the data needed to implement a custom device dialog.
old-location: image\devicedialogdata.htm
tech.root: image
ms.assetid: 8ddd3ad7-fa97-45a4-a124-ceccdfb93f7f
ms.date: 05/03/2018
ms.keywords: "*LPDEVICEDIALOGDATA, *PDEVICEDIALOGDATA, DEVICEDIALOGDATA, DEVICEDIALOGDATA structure [Imaging Devices], LPDEVICEDIALOGDATA, LPDEVICEDIALOGDATA structure pointer [Imaging Devices], PDEVICEDIALOGDATA, PDEVICEDIALOGDATA structure pointer [Imaging Devices], UIExt_58107635-73eb-474c-83a6-c46b7ea27dc2.xml, image.devicedialogdata, tagDEVICEDIALOGDATA, wiadevd/DEVICEDIALOGDATA, wiadevd/LPDEVICEDIALOGDATA, wiadevd/PDEVICEDIALOGDATA"
ms.topic: struct
req.header: wiadevd.h
req.include-header: Wiadevd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiadevd.h
api_name:
-	DEVICEDIALOGDATA
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA, *LPDEVICEDIALOGDATA, *PDEVICEDIALOGDATA
---

# tagDEVICEDIALOGDATA structure


## -description


The DEVICEDIALOGDATA structure contains all the data needed to implement a custom device dialog.


## -struct-fields




### -field cbSize

Specifies the size of this structure in bytes.


### -field hwndParent

Specifies the handle to the parent window of the dialog.


### -field pIWiaItemRoot

Points to an <b>IWiaItem</b> interface that represents the valid root item in the application item tree. For more information about this interface, see the Windows SDK documentation.


### -field dwFlags

Specifies the flags passed to <b>IWiaItem::DeviceDlg</b> and <b>IWiaDevMgr::GetImageDlg</b> by the calling program. These methods are described in the Windows SDK documentation. The possible values for this member are WIA_DEVICE_DIALOG_SINGLE_IMAGE and WIA_DEVICE_DIALOG_USE_COMMON_UI (defined in <i>Wiadef.h</i>).


### -field lIntent

Specifies the intents passed to <b>IWiaItem::DeviceDlg</b> and <b>IWiaDevMgr::GetImageDlg</b> by the calling program (see the Windows SDK documentation).


### -field lItemCount

Specifies the number of items in the array to which <b>ppIWiaItems</b> points.


### -field ppWiaItems

Array of IWiaItem interface pointers. Array must


## -remarks



The DEVICEDIALOGDATA structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545069">IWiaUIExtension::DeviceDialog</a> method.

The array specified in <i>ppIWiaItems</i> must be allocated using <b>CoTaskMemAlloc</b>. All interface pointers indicated in the array must be initialized using the <b>AddRef</b> COM method. See the Windows SDK documentation for descriptions of these functions.

The <b>IWiaPropertyStorage</b> interface is used to access information about the <b>IWiaItem</b> object's properties. Applications must query an item to obtain its <b>IWiaPropertyStorage</b> interface. See the Windows SDK documentation for descriptions of this interface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545069">IWiaUIExtension::DeviceDialog</a>
 

 

