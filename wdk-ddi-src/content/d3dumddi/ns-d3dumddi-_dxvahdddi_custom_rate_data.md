---
UID: NS:d3dumddi._DXVAHDDDI_CUSTOM_RATE_DATA
title: "_DXVAHDDDI_CUSTOM_RATE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_CUSTOM_RATE_DATA structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_custom_rate_data.htm
old-project: display
ms.assetid: 828c4c42-a74f-4737-b850-5c8299e5afd6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXVAHDDDI_CUSTOM_RATE_DATA, DXVA2_Structs_98dcb947-954a-4e8d-adea-3451814e89f9.xml, display.dxvahdddi_custom_rate_data, DXVAHDDDI_CUSTOM_RATE_DATA structure [Display Devices], d3dumddi/DXVAHDDDI_CUSTOM_RATE_DATA, DXVAHDDDI_CUSTOM_RATE_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_CUSTOM_RATE_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_CUSTOM_RATE_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_CUSTOM_RATE_DATA
---

# _DXVAHDDDI_CUSTOM_RATE_DATA structure


## -description


The DXVAHDDDI_CUSTOM_RATE_DATA structure describes the video content that a decode device processes. 


## -syntax


````
typedef struct _DXVAHDDDI_CUSTOM_RATE_DATA {
  DXVAHDDDI_RATIONAL CustomRate;
  UINT               OutputFrames;
  BOOL               InputInterlaced;
  UINT               InputFramesOrFields;
} DXVAHDDDI_CUSTOM_RATE_DATA;
````


## -struct-fields




### -field CustomRate


      [in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the input and output frame rate. 
     


### -field OutputFrames

[in] The number of frames that the driver outputs. 


### -field InputInterlaced

[in] A Boolean value that specifies whether the input stream is progressive (frame) or interlaced (field). 


### -field InputFramesOrFields

[in] The number of the input frames or fields. 


## -remarks


The driver can expose custom rates for the frame rate conversion or the inverse telecine. For example, the driver can provide the following information in the members of DXVAHDDDI_CUSTOM_RATE_DATA for the indicated operation:





## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_rational.md">DXVAHDDDI_RATIONAL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_CUSTOM_RATE_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

