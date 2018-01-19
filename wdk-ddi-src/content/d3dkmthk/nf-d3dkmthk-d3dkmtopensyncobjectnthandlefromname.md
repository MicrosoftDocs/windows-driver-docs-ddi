---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectNtHandleFromName
title: D3DKMTOpenSyncObjectNtHandleFromName function
author: windows-driver-content
description: D3DKMTOpenSyncObjectNtHandleFromName opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations.
old-location: display\d3dkmtopensyncobjectnthandlefromname.htm
old-project: display
ms.assetid: 29EF6C90-E25F-4E03-8834-EC2546B670AA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenSyncObjectNtHandleFromName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTOpenSyncObjectNtHandleFromName
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenSyncObjectNtHandleFromName function



## -description
<b>D3DKMTOpenSyncObjectNtHandleFromName</b> opens an NT handle for a named shared monitored fence object, similar to what <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopennthandlefromname.md">D3DKMTOpenNtHandleFromName</a> does for shared allocations.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenSyncObjectNtHandleFromName(
  _Inout_ D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensyncobjectnthandlefromname.md">D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME</a> structure that describes the operation.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation was performed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
         Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopennthandlefromname.md">D3DKMTOpenNtHandleFromName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenSyncObjectNtHandleFromName function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

