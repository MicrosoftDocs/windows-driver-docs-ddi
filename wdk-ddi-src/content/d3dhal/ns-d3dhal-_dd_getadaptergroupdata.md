---
UID: NS:d3dhal._DD_GETADAPTERGROUPDATA
title: "_DD_GETADAPTERGROUPDATA"
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETADAPTERGROUPDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETADAPTERGROUP.
old-location: display\dd_getadaptergroupdata.htm
old-project: display
ms.assetid: 8c427880-f809-4b58-8f69-d81a273d705c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DD_GETADAPTERGROUPDATA, DD_GETADAPTERGROUPDATA structure [Display Devices], _DD_GETADAPTERGROUPDATA, d3dhal/DD_GETADAPTERGROUPDATA, d3dstrct_6bd570c2-bccf-4c1c-8bfb-ff20d77b7201.xml, display.dd_getadaptergroupdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	DD_GETADAPTERGROUPDATA
product: Windows
targetos: Windows
req.typenames: DD_GETADAPTERGROUPDATA
---

# _DD_GETADAPTERGROUPDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_GETADAPTERGROUPDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETADAPTERGROUP.


## -syntax


````
typedef struct _DD_GETADAPTERGROUPDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  ULONG_PTR             ulUniqueAdapterGroupId;
  DWORD                 dwReserved1;
  DWORD                 dwReserved2;
} DD_GETADAPTERGROUPDATA;
````


## -struct-fields




### -field gdi2

Specifies a <a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data for the query.


### -field ulUniqueAdapterGroupId

Receives the identifier of the group of adapters that comprise the driver's multiple-head video card. The driver must provide a unique identifier for the master and all subordinate adapters within this group.


### -field dwReserved1

Specifies a reserved field. Driver should not read or write. Set to zero.


### -field dwReserved2

Specifies a reserved field. Driver should not read or write. Set to zero.


## -remarks



The runtime uses DD_GETADAPTERGROUPDATA in a query for the identity of the driver's group of adapters. This group shares video hardware like video memory and the 3D accelerator. The runtime mainly uses this query for dual-view video adapters. An application can request that surface resources (like textures and vertex buffers) be shared across adapters in a group and the runtime complies with that request.

The identifier in <b>ulUniqueAdapterGroupId</b> must be unique across drivers, including drivers from other hardware vendors. Therefore, it is recommended to report this identifier as a unique kernel-mode address that cannot be common with other multiple-head video cards. Note that the driver must report this identifier as nonzero. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>



<a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETADAPTERGROUPDATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

