---
UID: NF:d3dkmthk.D3DKMTGetMultisampleMethodList
title: D3DKMTGetMultisampleMethodList function
author: windows-driver-content
description: The D3DKMTGetMultisampleMethodList function retrieves a list of multiple-sample methods that are used for an allocation.
old-location: display\d3dkmtgetmultisamplemethodlist.htm
old-project: display
ms.assetid: 10084238-dfeb-42a5-9bf0-06cb9b4f440c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTGetMultisampleMethodList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTGetMultisampleMethodList
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetMultisampleMethodList function



## -description
The <b>D3DKMTGetMultisampleMethodList</b> function retrieves a list of multiple-sample methods that are used for an allocation.



## -syntax

````
NTSTATUS D3DKMTGetMultisampleMethodList(
  _Inout_ D3DKMT_GETMULTISAMPLEMETHODLIST *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md">D3DKMT_GETMULTISAMPLEMETHODLIST</a> structure that describes the list of multiple-sample methods for an allocation.


## -returns
<b>D3DKMTGetMultisampleMethodList</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The list of multiple-sample methods was successfully retrieved.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other NTSTATUS values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md">D3DKMT_GETMULTISAMPLEMETHODLIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetMultisampleMethodList function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

