---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
title: "_D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure describes the bit-block transfer (bitblt) state of the video processor to change and the data that is used to change the state.
old-location: display\d3dddiarg_dxvahd_setvideoprocessbltstate.htm
old-project: display
ms.assetid: ebcd58d7-f0b3-43ea-b08f-f0c2618902d7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE, D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure [Display Devices], UMDisplayDriver_param_Structs_fd02ddf9-535d-4c4b-a6fe-6c765170e6f9.xml, display.d3dddiarg_dxvahd_setvideoprocessbltstate, d3dumddi/D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE, D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
---

# _D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure


## -description


The D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure describes the bit-block transfer (bitblt) state of the video processor to change and the data that is used to change the state. 


## -syntax


````
typedef struct _D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE {
  HANDLE              hVideoProcessor;
  DXVAHDDDI_BLT_STATE State;
  UINT                DataSize;
  const VOID          *pData;
} D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE;
````


## -struct-fields




### -field hVideoProcessor

[in] A handle to the video processor whose bitblt state is changed.


### -field State

[in] A <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_blt_state.md">DXVAHDDDI_BLT_STATE</a>-typed value that indicates the type of bitblt to set.


### -field DataSize

[in] The size, in bytes, of the data that is used to change the bitblt state.


### -field pData

[in] A pointer to the data that is used to change the bitblt state. For more information about the types of data that <b>pData</b> can point to, see the values of the <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_blt_state.md">DXVAHDDDI_BLT_STATE</a> enumeration. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a>



<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_blt_state.md">DXVAHDDDI_BLT_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

