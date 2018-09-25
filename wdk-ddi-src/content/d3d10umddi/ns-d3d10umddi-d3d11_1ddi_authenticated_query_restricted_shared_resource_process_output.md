---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS.
old-location: display\d3d11_1ddi_authenticated_query_restricted_shared_resource_process_output.htm
ms.assetid: 91df98c0-185d-438c-b4e8-b4003a9c717f
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT, display.d3d11_1ddi_authenticated_query_restricted_shared_resource_process_output
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT structure


## -description


Contains the response to a <a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS</b>.


## -struct-fields




### -field Output

A  structure that contains a Message Authentication Code (MAC) and other data.


### -field ProcessIndex

The index of the process in the list of processes.




### -field ProcessIdentifier

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406372">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a> value that specifies the type of process.


### -field ProcessHandle

A process handle. If the <b>ProcessIdentifier</b> member equals <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b>, the <b>ProcessHandle</b> member contains a valid handle to a process. Otherwise, this member is ignored.


## -remarks



The Desktop Window Manager (DWM) process is identified by setting <b>ProcessIdentifier</b> equal to <b>D3D11_1DDI_PROCESSIDTYPE_DWM</b>. Other processes are identified by setting the process handle in <b>ProcessHandle</b> and setting <b>ProcessIdentifier</b> equal to <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406372">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a>
 

 

