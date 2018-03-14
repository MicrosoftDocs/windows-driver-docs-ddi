---
UID: NE:d3dkmthk._D3DKMT_DEVICESTATE_TYPE
title: "_D3DKMT_DEVICESTATE_TYPE"
author: windows-driver-content
description: The D3DKMT_DEVICESTATE_TYPE enumeration type contains values that indicate the status of a device.
old-location: display\d3dkmt_devicestate_type.htm
old-project: display
ms.assetid: 84570bac-63f1-4e34-919f-c150f9f0810e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_DEVICESTATE_EXECUTION, D3DKMT_DEVICESTATE_PAGE_FAULT, D3DKMT_DEVICESTATE_PRESENT, D3DKMT_DEVICESTATE_PRESENT_DWM, D3DKMT_DEVICESTATE_RESET, D3DKMT_DEVICESTATE_TYPE, D3DKMT_DEVICESTATE_TYPE enumeration [Display Devices], OpenGL_Structs_7446b76d-102c-4d61-bf39-ce1ca17ea036.xml, _D3DKMT_DEVICESTATE_TYPE, d3dkmthk/, d3dkmthk/D3DKMT_DEVICESTATE_EXECUTION, d3dkmthk/D3DKMT_DEVICESTATE_PAGE_FAULT, d3dkmthk/D3DKMT_DEVICESTATE_PRESENT, d3dkmthk/D3DKMT_DEVICESTATE_PRESENT_DWM, d3dkmthk/D3DKMT_DEVICESTATE_RESET, d3dkmthk/D3DKMT_DEVICESTATE_TYPE, display.d3dkmt_devicestate_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3DKMT_DEVICESTATE_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICESTATE_TYPE
---

# _D3DKMT_DEVICESTATE_TYPE enumeration


## -description


The D3DKMT_DEVICESTATE_TYPE enumeration type contains values that indicate the status of a device.


## -syntax


````
typedef enum _D3DKMT_DEVICESTATE_TYPE { 
  D3DKMT_DEVICESTATE_EXECUTION    = 1,
  D3DKMT_DEVICESTATE_PRESENT      = 2,
  D3DKMT_DEVICESTATE_RESET        = 3,
  D3DKMT_DEVICESTATE_PRESENT_DWM  = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  D3DKMT_DEVICESTATE_PAGE_FAULT   = 5,
#endif 
  
} D3DKMT_DEVICESTATE_TYPE;
````


## -enum-fields




### -field D3DKMT_DEVICESTATE_EXECUTION

The device execution state is retrieved.


### -field D3DKMT_DEVICESTATE_PRESENT

The device present state is retrieved.


### -field D3DKMT_DEVICESTATE_RESET

The device reset state is retrieved.


### -field D3DKMT_DEVICESTATE_PRESENT_DWM

The device present desktop window manager state is retrieved.


### -field D3DKMT_DEVICESTATE_PAGE_FAULT

The device page fault state is retrieved.


### -field D3DKMT_DEVICESTATE_PRESENT_QUEUE






## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>



 

 


