---
UID: NS:d3dkmthk._D3DKMT_OPENGLINFO
title: "_D3DKMT_OPENGLINFO"
author: windows-driver-content
description: The D3DKMT_OPENGLINFO structure describes OpenGL installable client driver (ICD) information.
old-location: display\d3dkmt_openglinfo.htm
old-project: display
ms.assetid: d8e571dd-b823-4cad-96b6-c7841a1234c4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_OPENGLINFO, D3DKMT_OPENGLINFO structure [Display Devices], OpenGL_Structs_93ba7fd7-969f-4edf-a6ce-38a135bcda83.xml, _D3DKMT_OPENGLINFO, d3dkmthk/D3DKMT_OPENGLINFO, display.d3dkmt_openglinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENGLINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENGLINFO
---

# _D3DKMT_OPENGLINFO structure


## -description


The D3DKMT_OPENGLINFO structure describes OpenGL installable client driver (ICD) information.


## -syntax


````
typedef struct _D3DKMT_OPENGLINFO {
  WCHAR UmdOpenGlIcdFileName[MAX_PATH];
  ULONG Version;
  ULONG Flags;
} D3DKMT_OPENGLINFO;
````


## -struct-fields




### -field UmdOpenGlIcdFileName

[out] An array of wide characters that contains the file name of the OpenGL ICD.


### -field Version

[out] The version of the OpenGL ICD.


### -field Flags

[in] This member is currently unused.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENGLINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

