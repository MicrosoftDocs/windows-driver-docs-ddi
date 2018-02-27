---
UID: NS:d3dumddi._D3DDDIVERTEXELEMENT
title: "_D3DDDIVERTEXELEMENT"
author: windows-driver-content
description: The D3DDDIVERTEXELEMENT structure describes an element in the array for a vertex shader declaration.
old-location: display\d3dddivertexelement.htm
old-project: display
ms.assetid: acb0fc1d-e360-4cb9-9b3b-7d8d03146cfd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIVERTEXELEMENT, D3DDDIVERTEXELEMENT structure [Display Devices], D3D_other_Structs_7f1e4f94-3964-4deb-b3b0-1b47f8953dfa.xml, _D3DDDIVERTEXELEMENT, d3dumddi/D3DDDIVERTEXELEMENT, display.d3dddivertexelement
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
-	D3DDDIVERTEXELEMENT
product: Windows
targetos: Windows
req.typenames: D3DDDIVERTEXELEMENT
---

# _D3DDDIVERTEXELEMENT structure


## -description


The D3DDDIVERTEXELEMENT structure describes an element in the array for a vertex shader declaration.


## -syntax


````
typedef struct _D3DDDIVERTEXELEMENT {
  USHORT Stream;
  USHORT Offset;
  UCHAR  Type;
  UCHAR  Method;
  UCHAR  Usage;
  UCHAR  UsageIndex;
} D3DDDIVERTEXELEMENT;
````


## -struct-fields




### -field Stream

[in] The number of the stream.


### -field Offset

[in] The offset (if any), in bytes, from the beginning of the stream to the start of the data.


### -field Type

[in] One of several predefined data types that define the data size. For more information about these types, see the D3DDECLTYPE enumeration type in the Microsoft Windows SDK documentation.


### -field Method

[in] The tessellator processing method. This method determines how the tessellator interprets and operates on the vertex data. For more information about these methods, see the D3DDECLMETHOD enumeration type in the Windows SDK documentation.


### -field Usage

[in] The intended use of the vertex data. For more information about the possible uses, see the D3DDECLUSAGE enumeration type in the Windows SDK documentation.


### -field UsageIndex

[in] A modification to the usage data that is specified in the <b>Usage</b> member. This modification enables multiple usage types to be specified.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIVERTEXELEMENT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

