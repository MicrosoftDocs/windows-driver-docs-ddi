---
UID: NS:wiadevd.tagDEVICEDIALOGDATA2
title: tagDEVICEDIALOGDATA2
author: windows-driver-content
description: The DEVICEDIALOGDATA2 structure contains all the data needed to implement a custom device dialog.
old-location: image\devicedialogdata2.htm
old-project: image
ms.assetid: 8bf83ec8-a620-48ba-90f0-7bfb8aebca1d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PDEVICEDIALOGDATA2, wiadevd/DEVICEDIALOGDATA2, PDEVICEDIALOGDATA2 structure pointer [Imaging Devices], UIExt_1afa7fd2-14a9-4997-81e7-0f00bbc55dd9.xml, LPDEVICEDIALOGDATA2, wiadevd/LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, DEVICEDIALOGDATA2 structure [Imaging Devices], *PDEVICEDIALOGDATA2, image.devicedialogdata2, *LPDEVICEDIALOGDATA2, wiadevd/PDEVICEDIALOGDATA2, tagDEVICEDIALOGDATA2, LPDEVICEDIALOGDATA2 structure pointer [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiadevd.h
req.include-header: Wiadevd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiadevd.h
apiname:
-	DEVICEDIALOGDATA2
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# tagDEVICEDIALOGDATA2 structure


## -description


The DEVICEDIALOGDATA2 structure contains all the data needed to implement a custom device dialog.


## -syntax


````
typedef struct tagDEVICEDIALOGDATA2 {
  DWORD     cbSize;
  IWiaItem2 *pIWiaItemRoot;
  DWORD     dwFlags;
  HWND      hwndParent;
  BSTR      bstrFolderName;
  BSTR      bstrFilename;
  LONG      lNumFiles;
  BSTR      *pbstrFilePaths;
  IWiaItem2 *pWiaItem;
} DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2;
````


## -struct-fields




### -field cbSize

Specifies the size, in bytes, of this structure.


### -field pIWiaItemRoot

Points to an <a href="http://go.microsoft.com/fwlink/p/?linkid=121992">IWiaItem2</a> interface that represents the valid root item in the application item tree.


### -field dwFlags

Specifies the flags passed to <a href="http://go.microsoft.com/fwlink/p/?linkid=121993">IWiaItem2::DeviceDlg</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=121994">IWiaDevMgr2::GetImageDlg</a> by the calling program. The possible values for this member are WIA_DEVICE_DIALOG_SINGLE_IMAGE and WIA_DEVICE_DIALOG_USE_COMMON_UI (defined in header file <i>Wiadef.h</i>).


### -field hwndParent

Specifies the handle to the parent window of the dialog.


### -field bstrFolderName

A string of type <b>BSTR</b> that contains the name of the destination folder to which the files obtained from WIA items are transferred.


### -field bstrFilename

A string of type <b>BSTR</b> that contains the file name template to be used for files transferred from WIA items to the destination folder designated by <b>bstrFolderName</b>. An arbitrary number of unique file names can be created by appending additional characters to the file name template. For more information about file name templates, see <a href="http://go.microsoft.com/fwlink/p/?linkid=121995">PathMakeUniqueName Function</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=121996">PathYetAnotherMakeUniqueName Function</a>.


### -field lNumFiles

The number of strings written to the <i>pbstrFilePaths</i> array.


### -field pbstrFilePaths

Pointer to an array of <b>BSTR</b> pointers. Each array element points to a <b>BSTR</b> that contains the destination name of a file that was successfully transferred to the folder identified by <b>bstrFolderName</b>. The method must allocate the storage for this member. For more information, see the following <b>Remarks</b> section.


### -field pWiaItem

Pointer to the <b>IWiaItem2</b> interface of the WIA item that transfers data to the file or files named in the <b>bstrFilePaths</b> array.


## -remarks



The DEVICEDIALOGDATA2 structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545053">IWiaUIExtension2::DeviceDialog</a> method.

The <b>DeviceDialog</b> method must allocate the <b>BSTR</b> pointer array specified in <i>pbstrFilePaths</i> by calling the <a href="http://go.microsoft.com/fwlink/p/?linkid=121997">CoTaskMemAlloc</a> function, and it must allocate each string pointed to by the array by calling the <a href="http://go.microsoft.com/fwlink/p/?linkid=121998">SysAllocString</a> function. The calling program is responsible for freeing the storage for the pointer array and strings.

To retain a reference to an <b>IWiaItem2</b> interface, the <b>DeviceDialog</b> method must call the <a href="http://go.microsoft.com/fwlink/p/?linkid=98432">IUnknown::AddRef</a> method on the interface before returning from the call.

To access information about an <b>IWiaItem2</b> object's properties, the <b>DeviceDialog</b> method must query the object to obtain its <a href="http://go.microsoft.com/fwlink/p/?linkid=122007">IWiaPropertyStorage</a> interface. To transfer data from an <b>IWiaItem2</b> object, the <b>DeviceDialog</b> method must query the object to obtain its <a href="http://go.microsoft.com/fwlink/p/?linkid=122008">IWiaTransfer</a> interface.




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?linkid=121995">PathMakeUniqueName</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=122007">IWiaPropertyStorage</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121993">IWiaItem2::DeviceDlg</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121997">CoTaskMemAlloc</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121992">IWiaItem2</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=122008">IWiaTransfer</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=98432">IUnknown::AddRef</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121998">SysAllocString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545053">IWiaUIExtension2::DeviceDialog</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121996">PathYetAnotherMakeUniqueName</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=121994">IWiaDevMgr2::GetImageDlg</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20DEVICEDIALOGDATA2 structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

