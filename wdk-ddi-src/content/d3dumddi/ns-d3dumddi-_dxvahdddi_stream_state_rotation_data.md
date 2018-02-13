---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ROTATION_DATA
title: "_DXVAHDDDI_STREAM_STATE_ROTATION_DATA"
author: windows-driver-content
description: Describes stream-state data that specifies the clockwise rotation of the display output surface.
old-location: display\dxvahdddi_stream_state_rotation_data.htm
old-project: display
ms.assetid: 1c874df6-6b47-4501-9eaf-7c07f0172580
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxvahdddi_stream_state_rotation_data, _DXVAHDDDI_STREAM_STATE_ROTATION_DATA, DXVAHDDDI_STREAM_STATE_ROTATION_DATA, DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure [Display Devices], d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dumddi.h
apiname:
-	DXVAHDDDI_STREAM_STATE_ROTATION_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ROTATION_DATA
---

# _DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure


## -description


Describes stream-state data that specifies the clockwise rotation of the display output surface.


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_ROTATION_DATA {
  BOOL               Enable;
  DXVAHDDDI_ROTATION Rotation;
} DXVAHDDDI_STREAM_STATE_ROTATION_DATA;
````


## -struct-fields




### -field Enable

A Boolean value that specifies whether the driver should rotate the output surface. The default value is <b>FALSE</b>, which indicates that rotation is disabled.


### -field Rotation

The clockwise degrees of rotation as specified by a <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_rotation.md">DXVAHDDDI_ROTATION</a> enumeration value.


## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_rotation.md">DXVAHDDDI_ROTATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

