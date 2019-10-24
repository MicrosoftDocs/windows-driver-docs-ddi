---
UID: NS:61883._AV_61883_REQUEST
title: _AV_61883_REQUEST (61883.h)
description: The AV_61883_REQUEST structure is used to pass requests to the IEC-61883 protocol driver.
old-location: ieee\av_61883_request.htm
tech.root: IEEE
ms.assetid: 697fbf86-5c99-4e35-bcb4-a6f5272cc987
ms.date: 02/15/2018
ms.keywords: "*PAV_61883_REQUEST, 61883/AV_61883_REQUEST, 61883/PAV_61883_REQUEST, 61883_structures_d914a3cc-63dd-4eaf-9d0f-2682e1da78c9.xml, AV_61883_REQUEST, AV_61883_REQUEST structure [Buses], IEEE.av_61883_request, PAV_61883_REQUEST, PAV_61883_REQUEST structure pointer [Buses], _AV_61883_REQUEST"
ms.topic: struct
f1_keywords:
 - "61883/AV_61883_REQUEST"
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- AV_61883_REQUEST
product:
- Windows
targetos: Windows
req.typenames: AV_61883_REQUEST, *PAV_61883_REQUEST
---

# _AV_61883_REQUEST structure


## -description


The AV_61883_REQUEST structure is used to pass requests to the IEC-61883 protocol driver.


## -struct-fields




### -field Function

Determines the type of request. Each request type is documented under the value of <b>Function</b> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IEC-61883 Protocol I/O Requests</a>.


### -field Version

The device driver interface (DDI) version for the request. The <a href="https://docs.microsoft.com/previous-versions/ff537219(v=vs.85)">INIT_61883_HEADER</a> macro initializes <b>Version</b> to CURRENT_61883_DDI_VERSION.


### -field Flags

Flags specific to the request. For details, see the reference page for the request. Drivers must set this member to zero for requests that do not use flags.


### -field GetUnitInfo

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_get_unit_info">GET_UNIT_INFO</a> structure, used if the <b>Function</b> member is <a href="https://docs.microsoft.com/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a>.


### -field SetUnitInfo

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_set_unit_info">SET_UNIT_INFO</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>.


### -field GetPlugHandle

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_get_plug_handle">CMP_GET_PLUG_HANDLE</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536979">Av61883_GetPlugHandle</a>.


### -field GetPlugState

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_get_plug_state">CMP_GET_PLUG_STATE</a> structure, used if the <b>Function</b> member is <a href="https://docs.microsoft.com/previous-versions/ff536980(v=vs.85)">Av61883_GetPlugState</a>.


### -field Connect

A CMP_CONNECT structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536958">Av61883_Connect</a>.


### -field Disconnect

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_disconnect">CMP_DISCONNECT</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536966">Av61883_Disconnect</a>.


### -field AttachFrame

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_attach_frame">CIP_ATTACH_FRAME</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536950">Av61883_AttachFrame</a>.


### -field CancelFrame

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_cancel_frame">CIP_CANCEL_FRAME</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536956">Av61883_CancelFrame</a>.


### -field Talk

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_talk">CIP_TALK</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537007">Av61883_Talk</a>.


### -field Listen

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_listen">CIP_LISTEN</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536985">Av61883_Listen</a>.


### -field Stop

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_stop">CIP_STOP</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537005">Av61883_Stop</a>.


### -field Request

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_send_request">FCP_SEND_REQUEST</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536992">Av61883_SendFcpResponse</a>.


### -field Response

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_get_response">FCP_GET_RESPONSE</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536977">Av61883_GetFcpResponse</a>.


### -field SendRequest

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_send_request">FCP_SEND_REQUEST</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536992">Av61883_SendFcpResponse</a>.


### -field GetResponse

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_get_response">FCP_GET_RESPONSE</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536977">Av61883_GetFcpResponse</a>.


### -field GetRequest

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_get_request">FCP_GET_REQUEST</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536974">Av61883_GetFcpRequest</a>.


### -field SendResponse

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_send_response">FCP_SEND_RESPONSE</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536992">Av61883_SendFcpResponse</a>.


### -field SetFcpNotify

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_set_fcp_notify">SET_FCP_NOTIFY</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536993">Av61883_SetFcpNotify</a>.


### -field CreatePlug

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_create_plug">CMP_CREATE_PLUG</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536961">Av61883_CreatePlug</a>.


### -field DeletePlug

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_delete_plug">CMP_DELETE_PLUG</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536964">Av61883_DeletePlug</a>.


### -field SetPlug

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_set_plug">CMP_SET_PLUG</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536995">Av61883_SetPlug</a>.


### -field BusResetNotify

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_bus_reset_notify">BUS_RESET_NOTIFY</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536955">Av61883_BusResetNotify</a>.


### -field SetUnitDirectory

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_set_unit_directory">SET_UNIT_DIRECTORY</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536998">Av61883_SetUnitDirectory</a>.


### -field MonitorPlugs

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_monitor_plugs">CMP_MONITOR_PLUGS</a> structure, used if the <b>Function</b> member is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>.


## -remarks



The <b>Parameters-></b><b>Others.Arguments1</b> member of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ni-61883-ioctl_61883_class">IOCTL_61883_CLASS</a> IRP points to an AV_61883_REQUEST structure. The IEC-61883 protocol driver uses the request structure to determine the type of request made by the client driver, and also to return the results of the operation. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IEC-61883 Protocol I/O Requests</a> for a description of the behavior of each request.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff537219(v=vs.85)">INIT_61883_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ni-61883-ioctl_61883_class">IOCTL_61883_CLASS</a>
 

 

