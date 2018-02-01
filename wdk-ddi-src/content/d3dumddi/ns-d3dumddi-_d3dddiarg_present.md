---
UID: NS:d3dumddi._D3DDDIARG_PRESENT
title: "_D3DDDIARG_PRESENT"
author: windows-driver-content
description: The D3DDDIARG_PRESENT structure describes a resource to display.
old-location: display\d3dddiarg_present.htm
old-project: display
ms.assetid: ee872d01-4bc6-46ce-80b7-3f73dd1a89ab
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_PRESENT, d3dumddi/D3DDDIARG_PRESENT, display.d3dddiarg_present, D3DDDIARG_PRESENT structure [Display Devices], _D3DDDIARG_PRESENT, UMDisplayDriver_param_Structs_1406aa28-1355-4e46-886f-9121fcbd7750.xml
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
-	D3DDDIARG_PRESENT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_PRESENT
---

# _D3DDDIARG_PRESENT structure


## -description


The D3DDDIARG_PRESENT structure describes a resource to display.


## -syntax


````
typedef struct _D3DDDIARG_PRESENT {
  HANDLE                   hSrcResource;
  UINT                     SrcSubResourceIndex;
  HANDLE                   hDstResource;
  UINT                     DstSubResourceIndex;
  D3DDDI_PRESENTFLAGS      Flags;
  D3DDDI_FLIPINTERVAL_TYPE FlipInterval;
} D3DDDIARG_PRESENT;
````


## -struct-fields




### -field hSrcResource

[in] A handle to the source resource to display. <b>hSrcResource</b> can be <b>NULL</b> if the user-mode display driver should perform a color-fill operation to the screen.


### -field SrcSubResourceIndex

[in] The zero-based index into the source resource, which is specified by the handle in the <b>hSrcResource</b> member. This index indicates the subresource or surface to display.


### -field hDstResource

[in] A handle to the destination resource to display to. If <b>NULL</b>, the user-mode display driver is informed that a color-fill operation will occur, but the user-mode driver is not expected to perform the operation. The display miniport driver does the actual color-fill operation and will be informed of the color value at that time.


### -field DstSubResourceIndex


      [in] The zero-based index into the destination resource, which is specified by the handle in the <b>hDstResource</b> member. This index indicates the subresource or surface to display to.
     


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_presentflags.md">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display. 


### -field FlipInterval

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_PRESENT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

