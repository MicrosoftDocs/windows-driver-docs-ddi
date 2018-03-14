---
UID: NS:dispmprt._DXGK_CHILD_STATUS
title: "_DXGK_CHILD_STATUS"
author: windows-driver-content
description: The DXGK_CHILD_STATUS structure contains members that indicate the status of a child device of the display adapter.
old-location: display\dxgk_child_status.htm
old-project: display
ms.assetid: e2aba049-b51f-49b9-b0bb-c98c318dea86
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_CHILD_STATUS, DXGK_CHILD_STATUS, DXGK_CHILD_STATUS structure [Display Devices], DmStructs_9a370d5a-9ca8-4c4f-a5cf-3361847d65e7.xml, PDXGK_CHILD_STATUS, PDXGK_CHILD_STATUS structure pointer [Display Devices], _DXGK_CHILD_STATUS, display.dxgk_child_status, dispmprt/DXGK_CHILD_STATUS, dispmprt/PDXGK_CHILD_STATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_CHILD_STATUS
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_STATUS, *PDXGK_CHILD_STATUS
---

# _DXGK_CHILD_STATUS structure


## -description


The DXGK_CHILD_STATUS structure contains members that indicate the status of a child device of the display adapter.


## -syntax


````
typedef struct _DXGK_CHILD_STATUS {
  DXGK_CHILD_STATUS_TYPE Type;
  ULONG                  ChildUid;
  union {
    struct {
      BOOLEAN Connected;
    } HotPlug;
    struct {
      UCHAR Angle;
    } Rotation;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
    struct {
      BOOLEAN                         Connected;
      D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY MiracastMonitorType;
    } Miracast;
#endif 
  };
} DXGK_CHILD_STATUS, *PDXGK_CHILD_STATUS;
````


## -struct-fields




### -field Type

A member of the <a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a> enumeration that indicates the type of status being requested.


### -field ChildUid

An integer, created previously by the display miniport driver, that identifies the child device for which status is being requested.


### -field HotPlug


### -field HotPlug.Connected

If <b>Type</b> is equal to <a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a>.<b>StatusConnection</b>, indicates whether the child device has external hardware (for example, a monitor) connected to it. A value of <b>TRUE</b> indicates that hardware is connected; <b>FALSE</b> indicates that hardware is not connected.


### -field Rotation


### -field Rotation.Angle

If <b>Type</b> is equal to <a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a>.<b>StatusRotation</b>,  indicates the angle of rotation of the display connected to the child device.


### -field Miracast

Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.


### -field Miracast.Connected

If <b>Type</b> is equal to <a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a>.<b>StatusMiracast</b>, indicates whether a Miracast connected session has started. A value of <b>TRUE</b> indicates that a new monitor has been connected to the Miracast sink, or that the Miracast session has started with a monitor connected. <b>FALSE</b> indicates that the monitor that was connected to the Miracast sink has been unplugged, or that the Miracast session has been stopped.

For more info, see <a href="https://msdn.microsoft.com/1645E14A-EC4A-4EB8-9AFA-6DF0466D2B1A">Wireless displays (Miracast)</a>.


### -field Miracast.MiracastMonitorType

If the <b>Connected</b> member of the <b>Miracast</b> embedded structure is <b>TRUE</b>, indicates the connector type of the connection between the Miracast sink and the monitor or TV. 

Alternately, if <b>Connected</b> is <b>TRUE</b> and the Miracast sink is embedded in the monitor or TV, the display miniport driver should set this value to <b>D3DKMDT_VOT_MIRACAST</b>.

If the driver doesn't know the monitor connection state, it should set this value to the last monitor connection state from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_video_output_technology.md">D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY</a> enumeration that it reported to the operating system.

For more info, see <a href="https://msdn.microsoft.com/1645E14A-EC4A-4EB8-9AFA-6DF0466D2B1A">Wireless displays (Miracast)</a>.


## -see-also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_video_output_technology.md">D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_indicate_child_status.md">DxgkCbIndicateChildStatus</a>



<a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a>



 

 


