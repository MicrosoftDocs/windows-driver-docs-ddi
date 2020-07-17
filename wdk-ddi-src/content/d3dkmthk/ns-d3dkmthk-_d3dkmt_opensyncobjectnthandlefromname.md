---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
title: _D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME (d3dkmthk.h)
description: D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME is used with D3DKMTOpenSyncObjectNtHandleFromName to open an NT handle for a named shared monitored fence object.
old-location: display\d3dkmt_opensyncobjectnthandlefromname.htm
ms.assetid: 6435D3B7-A1B7-4417-8272-C505A5FA500E
ms.date: 05/10/2018
keywords: ["_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME structure"]
ms.keywords: D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME, D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME structure [Display Devices], _D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME, d3dkmthk/D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME, display.d3dkmt_opensyncobjectnthandlefromname
f1_keywords:
 - "d3dkmthk/D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME"
 - "D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME
---

# _D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME structure


## -description


<b>D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensyncobjectnthandlefromname">D3DKMTOpenSyncObjectNtHandleFromName</a> to open an NT handle for a named shared monitored fence object.


## -struct-fields




### -field dwDesiredAccess

[in] Access attributes for opening a shared monitored fence sync object, such as <b>D3DDDI_SYNC_OBJECT_WAIT</b>, <b>D3DDDI_SYNC_OBJECT_SIGNAL</b>, or <b>D3DDDI_SYNC_OBJECT_ALL_ACCESS</b>.


### -field pObjAttrib

[in] Object attributes for opening the object handle, including the shared object name information.


### -field hNtHandle

[out] NT handle to the sync object that can be used to open it via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensyncobjectfromnthandle2">D3DKMTOpenSyncObjectFromNtHandle2</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensyncobjectfromnthandle2">D3DKMTOpenSyncObjectFromNtHandle2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensyncobjectnthandlefromname">D3DKMTOpenSyncObjectNtHandleFromName</a>
 

 

