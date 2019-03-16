---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectFromNtHandle2
title: D3DKMTOpenSyncObjectFromNtHandle2 function (d3dkmthk.h)
description: D3DKMTOpenSyncObjectFromNtHandle2 opens a monitored fence object from an NT handle previously created by D3DKMTShareObjects.
old-location: display\d3dkmtopensyncobjectfromnthandle2.htm
ms.assetid: E3295F4F-AB51-4EBB-8B9F-E47BBA52AF47
ms.date: 05/10/2018
ms.keywords: D3DKMTOpenSyncObjectFromNtHandle2, D3DKMTOpenSyncObjectFromNtHandle2 function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle2, display.d3dkmtopensyncobjectfromnthandle2
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTOpenSyncObjectFromNtHandle2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenSyncObjectFromNtHandle2 function

## -description

<b>D3DKMTOpenSyncObjectFromNtHandle2</b> opens a monitored fence object from an NT handle previously created by <a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a>.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906796">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh780251">D3DKMTShareObjects</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906796">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2</a>
 

 

