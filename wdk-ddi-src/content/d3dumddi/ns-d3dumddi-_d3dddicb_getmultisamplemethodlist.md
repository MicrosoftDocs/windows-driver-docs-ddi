---
UID: NS:d3dumddi._D3DDDICB_GETMULTISAMPLEMETHODLIST
title: "_D3DDDICB_GETMULTISAMPLEMETHODLIST"
author: windows-driver-content
description: The D3DDDICB_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.
old-location: display\d3dddicb_getmultisamplemethodlist.htm
old-project: display
ms.assetid: 07cabd0e-5b5c-42ff-9b2a-57bec527d690
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDICB_GETMULTISAMPLEMETHODLIST, _D3DDDICB_GETMULTISAMPLEMETHODLIST, D3DDDICB_GETMULTISAMPLEMETHODLIST, D3DDDICB_GETMULTISAMPLEMETHODLIST structure [Display Devices], D3D_param_Structs_11da91d5-a4e6-4d24-b2b1-3645003ff25e.xml, display.d3dddicb_getmultisamplemethodlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	D3DDDICB_GETMULTISAMPLEMETHODLIST
product: Windows
targetos: Windows
req.typenames: D3DDDICB_GETMULTISAMPLEMETHODLIST
---

# _D3DDDICB_GETMULTISAMPLEMETHODLIST structure


## -description


The D3DDDICB_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.


## -syntax


````
typedef struct _D3DDDICB_GETMULTISAMPLEMETHODLIST {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           Width;
  UINT                           Height;
  D3DDDIFORMAT                   Format;
  D3DDDI_MULTISAMPLINGMETHOD     *pMethodList;
  UINT                           MethodCount;
} D3DDDICB_GETMULTISAMPLEMETHODLIST;
````


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the allocation is on. 


### -field Width

[in] The width of the allocation, in pixels.


### -field Height

[in] The height of the allocation, in pixels.


### -field Format

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation.


### -field pMethodList

[out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_multisamplingmethod.md">D3DDDI_MULTISAMPLINGMETHOD</a> structures that describe the list of multiple-sampling methods that are used for the allocation or <b>NULL</b>.


### -field MethodCount

[in/out] On input, the number of elements that the buffer at <b>pMethodList</b> can hold. On output, this member specifies the required number of elements that the buffer at <b>pMethodList</b> should hold. 


## -remarks


If the runtime returns a non-<b>NULL</b> value in the <b>pMethodList</b> member, the runtime returns a value in the <b>MethodCount</b> member that represents the number of elements that the array can hold. If the runtime returns <b>NULL</b> at <b>pMethodList</b>, the runtime returns a value in <b>MethodCount</b> that represents the size of the array buffer that is required, in number of elements. 



## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb.md">pfnGetMultisampleMethodListCb</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_multisamplingmethod.md">D3DDDI_MULTISAMPLINGMETHOD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_GETMULTISAMPLEMETHODLIST structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

