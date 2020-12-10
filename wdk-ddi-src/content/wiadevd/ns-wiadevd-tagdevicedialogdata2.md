---
UID: NS:wiadevd.tagDEVICEDIALOGDATA2
title: tagDEVICEDIALOGDATA2 (wiadevd.h)
description: The DEVICEDIALOGDATA2 structure contains all the data needed to implement a custom device dialog.
old-location: image\devicedialogdata2.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["tagDEVICEDIALOGDATA2 structure"]
ms.keywords: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, DEVICEDIALOGDATA2 structure [Imaging Devices], LPDEVICEDIALOGDATA2, LPDEVICEDIALOGDATA2 structure pointer [Imaging Devices], PDEVICEDIALOGDATA2, PDEVICEDIALOGDATA2 structure pointer [Imaging Devices], UIExt_1afa7fd2-14a9-4997-81e7-0f00bbc55dd9.xml, image.devicedialogdata2, tagDEVICEDIALOGDATA2, wiadevd/DEVICEDIALOGDATA2, wiadevd/LPDEVICEDIALOGDATA2, wiadevd/PDEVICEDIALOGDATA2"
req.header: wiadevd.h
req.include-header: Wiadevd.h
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
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
f1_keywords:
 - tagDEVICEDIALOGDATA2
 - wiadevd/tagDEVICEDIALOGDATA2
 - LPDEVICEDIALOGDATA2
 - wiadevd/LPDEVICEDIALOGDATA2
 - DEVICEDIALOGDATA2
 - wiadevd/DEVICEDIALOGDATA2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiadevd.h
api_name:
 - DEVICEDIALOGDATA2
---

# tagDEVICEDIALOGDATA2 structure


## -description

The DEVICEDIALOGDATA2 structure contains all the data needed to implement a custom device dialog.

## -struct-fields

### -field cbSize

Specifies the size, in bytes, of this structure.

### -field pIWiaItemRoot

Points to an [IWiaItem2](/windows/win32/wia/-wia-iwiaitem2) interface that represents the valid root item in the application item tree.

### -field dwFlags

Specifies the flags passed to [IWiaItem2::DeviceDlg](/windows/win32/wia/-wia-iwiaitem2-devicedlg) and [IWiaDevMgr2::GetImageDlg](/windows/win32/wia/-wia-iwiadevmgr2-getimagedlg) by the calling program. The possible values for this member are WIA_DEVICE_DIALOG_SINGLE_IMAGE and WIA_DEVICE_DIALOG_USE_COMMON_UI (defined in header file *Wiadef.h*).

### -field hwndParent

Specifies the handle to the parent window of the dialog.

### -field bstrFolderName

A string of type **BSTR** that contains the name of the destination folder to which the files obtained from WIA items are transferred.

### -field bstrFilename

A string of type **BSTR** that contains the file name template to be used for files transferred from WIA items to the destination folder designated by **bstrFolderName**. An arbitrary number of unique file names can be created by appending additional characters to the file name template. For more information about file name templates, see [PathMakeUniqueName](/windows/win32/api/shlobj_core/nf-shlobj_core-pathmakeuniquename) and [PathYetAnotherMakeUniqueName](/windows/win32/api/shlobj_core/nf-shlobj_core-pathyetanothermakeuniquename).

### -field lNumFiles

The number of strings written to the *pbstrFilePaths* array.

### -field pbstrFilePaths

Pointer to an array of **BSTR** pointers. Each array element points to a **BSTR** that contains the destination name of a file that was successfully transferred to the folder identified by **bstrFolderName**. The method must allocate the storage for this member. For more information, see the following **Remarks** section.

### -field pWiaItem

Pointer to the **IWiaItem2** interface of the WIA item that transfers data to the file or files named in the **bstrFilePaths** array.

## -remarks

The DEVICEDIALOGDATA2 structure is used by the [IWiaUIExtension2::DeviceDialog](/previous-versions/windows/hardware/drivers/ff545053(v=vs.85)) method.

The **DeviceDialog** method must allocate the **BSTR** pointer array specified in *pbstrFilePaths* by calling the [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) function, and it must allocate each string pointed to by the array by calling the [SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) function. The calling program is responsible for freeing the storage for the pointer array and strings.

To retain a reference to an **IWiaItem2** interface, the **DeviceDialog** method must call the [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) method on the interface before returning from the call.

To access information about an **IWiaItem2** object's properties, the **DeviceDialog** method must query the object to obtain its [IWiaPropertyStorage](/windows/win32/api/wia_xp/nn-wia_xp-iwiapropertystorage) interface. To transfer data from an **IWiaItem2** object, the **DeviceDialog** method must query the object to obtain its [IWiaTransfer](/windows/win32/wia/-wia-iwiatransfer) interface.

## -see-also

[CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)

[IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)

[IWiaDevMgr2::GetImageDlg](/windows/win32/wia/-wia-iwiadevmgr2-getimagedlg)

[IWiaItem2](/windows/win32/wia/-wia-iwiaitem2)

[IWiaItem2::DeviceDlg](/windows/win32/wia/-wia-iwiaitem2-devicedlg)

[IWiaPropertyStorage](/windows/win32/api/wia_xp/nn-wia_xp-iwiapropertystorage)

[IWiaTransfer](/windows/win32/wia/-wia-iwiatransfer)

[IWiaUIExtension2::DeviceDialog](/previous-versions/windows/hardware/drivers/ff545053(v=vs.85))

[PathMakeUniqueName](/windows/win32/api/shlobj_core/nf-shlobj_core-pathmakeuniquename)

[PathYetAnotherMakeUniqueName Function](/windows/win32/api/shlobj_core/nf-shlobj_core-pathyetanothermakeuniquename)

[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)
