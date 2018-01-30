---
UID: NE:d3dkmthk._D3DKMT_DEVICEEXECUTION_STATE
title: "_D3DKMT_DEVICEEXECUTION_STATE"
author: windows-driver-content
description: Contains values that indicate the execution status for a device.
old-location: display\d3dkmt_deviceexecution_state.htm
old-project: display
ms.assetid: 31935433-6fa4-4d1a-9ad4-879353102e71
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT, d3dkmthk/, D3DKMT_DEVICEEXECUTION_RESET, d3dkmthk/D3DKMT_DEVICEEXECUTION_RESET, d3dkmthk/D3DKMT_DEVICEEXECUTION_ACTIVE, d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT, display.d3dkmt_deviceexecution_state, d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY, D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT, D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT, D3DKMT_DEVICEEXECUTION_STOPPED, OpenGL_Structs_35637d1a-f40f-49f5-b774-777e02f22b68.xml, D3DKMT_DEVICEEXECUTION_STATE, D3DKMT_DEVICEEXECUTION_STATE enumeration [Display Devices], D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY, _D3DKMT_DEVICEEXECUTION_STATE, D3DKMT_DEVICEEXECUTION_ACTIVE, d3dkmthk/D3DKMT_DEVICEEXECUTION_STATE, d3dkmthk/D3DKMT_DEVICEEXECUTION_HUNG, d3dkmthk/D3DKMT_DEVICEEXECUTION_STOPPED, D3DKMT_DEVICEEXECUTION_HUNG
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_DEVICEEXECUTION_STATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICEEXECUTION_STATE
---

# _D3DKMT_DEVICEEXECUTION_STATE enumeration


## -description


The <b>D3DKMT_DEVICEEXECUTION_STATE</b> enumeration type contains values that indicate the execution status for a device.


## -syntax


````
typedef enum _D3DKMT_DEVICEEXECUTION_STATE { 
  D3DKMT_DEVICEEXECUTION_ACTIVE              = 1,
  D3DKMT_DEVICEEXECUTION_RESET               = 2,
  D3DKMT_DEVICEEXECUTION_HUNG                = 3,
  D3DKMT_DEVICEEXECUTION_STOPPED             = 4,
  D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY   = 5,
  D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT      = 6,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT  = 7,
#endif 
  
} D3DKMT_DEVICEEXECUTION_STATE;
````


## -enum-fields




### -field D3DKMT_DEVICEEXECUTION_ACTIVE

The device is actively executing.


### -field D3DKMT_DEVICEEXECUTION_RESET

The device is reset.


### -field D3DKMT_DEVICEEXECUTION_HUNG

The device is hung. The device is unable to continue.


### -field D3DKMT_DEVICEEXECUTION_STOPPED


      The device is stopped.
     


### -field D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY

Even after the video memory manager split the DMA buffer, the video memory manager could not page-in all of the required allocations into video memory at the same time. The device is unable to continue.


### -field D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT

The display miniport driver reported a fault while processing a DMA buffer for the device. The device is unable to continue.


### -field D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT

The display miniport driver reported a page fault while processing a DMA buffer for the device. The device is unable to continue.





## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEVICEEXECUTION_STATE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

