---
UID: NS:d3dkmthk._D3DKMT_ADAPTERREGISTRYINFO
title: "_D3DKMT_ADAPTERREGISTRYINFO"
author: windows-driver-content
description: The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.
old-location: display\d3dkmt_adapterregistryinfo.htm
old-project: display
ms.assetid: b1bad6e8-8592-457a-8f66-40fc5040ae96
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Structs_0d97d602-7fc3-40a2-aa06-2966a6fc04f7.xml, D3DKMT_ADAPTERREGISTRYINFO, D3DKMT_ADAPTERREGISTRYINFO structure [Display Devices], _D3DKMT_ADAPTERREGISTRYINFO, display.d3dkmt_adapterregistryinfo, d3dkmthk/D3DKMT_ADAPTERREGISTRYINFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_ADAPTERREGISTRYINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_ADAPTERREGISTRYINFO
---

# _D3DKMT_ADAPTERREGISTRYINFO structure


## -description


The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter. 


## -syntax


````
typedef struct _D3DKMT_ADAPTERREGISTRYINFO {
  WCHAR AdapterString[MAX_PATH];
  WCHAR BiosString[MAX_PATH];
  WCHAR DacType[MAX_PATH];
  WCHAR ChipType[MAX_PATH];
} D3DKMT_ADAPTERREGISTRYINFO;
````


## -struct-fields




#### - AdapterString

[out] A string that contains the name of the graphics adapter.


#### - BiosString

[out] A string that contains the name of the BIOS for the graphics adapter.


#### - DacType

[out] A string that contains the DAC type for the graphics adapter.


#### - ChipType

[out] A string that contains the chip type for the graphics adapter.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ADAPTERREGISTRYINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

