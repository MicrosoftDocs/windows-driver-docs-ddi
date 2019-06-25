---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE (d3d10umddi.h)
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE.
old-location: display\d3d11_1ddi_authenticated_configure_shared_resource.htm
ms.assetid: 004046d1-552e-43a5-94b1-30b113e8b40e
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE, D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE, display.d3d11_1ddi_authenticated_configure_shared_resource
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE structure


## -description


Contains input data for a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</b>.


## -struct-fields




### -field Parameters

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data. 


### -field ProcessType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_process_identifier_type">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a> value that specifies the type of process. To specify the DWM process, set this member to <b>D3D11_1DDI_PROCESSIDTYPE_DWM</b>. Otherwise, set this member to <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b> and set the <b>ProcessHandle</b> member to a valid handle.


### -field ProcessHandle

A process handle. If the <b>ProcessType</b> member equals <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b>, the <b>ProcessHandle</b> member specifies a handle to a process. Otherwise, the value is ignored.


### -field AllowAccess

If <b>TRUE</b>, the specified process has access to restricted shared resources.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_process_identifier_type">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a>
 

 

