---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
title: "_DXVAHDDDI_STREAM_STATE_PRIVATE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state.
old-location: display\dxvahdddi_stream_state_private_data.htm
old-project: display
ms.assetid: 1352392f-62d4-46aa-aa59-651309c36e6f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, DXVA2_Structs_4c06fc77-dcae-41fa-b831-c3918ddbf467.xml, display.dxvahdddi_stream_state_private_data, d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
---

# _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state. 


## -syntax


````
typedef struct _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA {
  GUID Guid;
  UINT DataSize;
  VOID *pData;
} DXVAHDDDI_STREAM_STATE_PRIVATE_DATA;
````


## -struct-fields




### -field Guid

[in] A GUID that identifies the private stream state.  


### -field DataSize

[in] The size, in bytes, of the private stream-state data. 


### -field pData

[in/out] A pointer to the private stream-state data. The caller sets <b>pData</b> to <b>NULL</b> to retrieve the size of the private stream-state data. 


## -remarks



Unlike other stream states (<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_stream_state.md">DXVAHDDDI_STREAM_STATE</a>), the Direct3D runtime does not maintain the private stream state. An application and the driver communicates the private stream state directly through a proprietary manner, which consists of setting and retrieving the private stream state. 

To set private stream state, the application causes the Direct3D runtime to specify the DXVAHDDDI_STREAM_STATE_PRIVATE state in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function. To retrieve private stream state, the application causes the Direct3D runtime to call the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate.md">GetVideoProcessStreamStatePrivate</a> function. 




## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_stream_state.md">DXVAHDDDI_STREAM_STATE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate.md">GetVideoProcessStreamStatePrivate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

