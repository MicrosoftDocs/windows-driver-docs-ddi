---
UID: NS:d3dhal._DD_GETFORMATCOUNTDATA
title: "_DD_GETFORMATCOUNTDATA"
author: windows-driver-content
description: DirectX 8.0 and later versions only. DD_GETFORMATCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMATCOUNT.
old-location: display\dd_getformatcountdata.htm
old-project: display
ms.assetid: 5f334f48-a262-4b09-98c4-766039de3f0e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DD_GETFORMATCOUNTDATA, d3dstrct_610983cc-4f8a-4c16-b60b-960dbf0c58e9.xml, d3dhal/DD_GETFORMATCOUNTDATA, DD_GETFORMATCOUNTDATA structure [Display Devices], display.dd_getformatcountdata, _DD_GETFORMATCOUNTDATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	DD_GETFORMATCOUNTDATA
product: Windows
targetos: Windows
req.typenames: DD_GETFORMATCOUNTDATA
---

# _DD_GETFORMATCOUNTDATA structure


## -description



   DirectX 8.0 and later versions only.
   

DD_GETFORMATCOUNTDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETFORMATCOUNT.


## -syntax


````
typedef struct _DD_GETFORMATCOUNTDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwFormatCount;
  DWORD                 dwReserved;
} DD_GETFORMATCOUNTDATA;
````


## -struct-fields




### -field gdi2

Specifies a <a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwFormatCount

Receives the number of supported surface formats.


### -field dwReserved

<b>DirectX 8.0 and 8.1 versions only.</b> Specifies a reserved field. Driver should not read or write.

<b>DirectX 9.0 and later versions only.</b> Specifies the version of the DirectX runtime being used by the application. This member is set to DD_RUNTIME_VERSION, which is 0x00000900 for DirectX 9.0.


## -remarks



To handle the D3DGDI2_TYPE_GETFORMATCOUNT request, the driver must store the number of DirectX 8.0 and later DDI style surface formats that it supports in the <b>dwFormatCount</b> member of DD_GETFORMATCOUNTDATA. For more information, see <a href="https://msdn.microsoft.com/5e60d6e3-d0a2-4b52-86cb-06de839f970a">The Texture Format List</a>.




## -see-also

<a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETFORMATCOUNTDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

