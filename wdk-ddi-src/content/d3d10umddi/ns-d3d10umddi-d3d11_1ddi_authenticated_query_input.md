---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_INPUT (d3d10umddi.h)
description: Contains input data for the QueryAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_query_input.htm
ms.assetid: f7a4fb53-aa01-4279-a59a-fd92b0ceeab7
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_QUERY_INPUT structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ATTRIBUTES, D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE, D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION, D3D11_1DDI_AUTHENTICATED_QUERY_CURRENT_ENCRYPTION_WHEN_ACCESSIBLE, D3D11_1DDI_AUTHENTICATED_QUERY_DEVICE_HANDLE, D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID, D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID_COUNT, D3D11_1DDI_AUTHENTICATED_QUERY_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_INPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID, D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT, D3D11_1DDI_AUTHENTICATED_QUERY_PROTECTION, D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS, D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_COUNT, D3D11_1DDI_AUTHENTICATED_QUERY_UNRESTRICTED_PROTECTED_SHARED_RESOURCE_COUNT, d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_INPUT, display.d3d11_1ddi_authenticated_query_input
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
f1_keywords:
 - D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
 - d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_INPUT structure


## -description

Contains input data for the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> function.

## -struct-fields

### -field QueryType

A GUID that specifies the query. The following GUIDs are defined.



#### D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ATTRIBUTES

Returns the type of I/O bus that is used to send data to the GPU.

Output data structure: 


<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_acessibility_output">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE

Returns the type of authenticated channel.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_channel_type_output">D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION

Returns handles to the cryptographic session and Direct3D device that are associated with a specified DirectX Video Acceleration 2 (DXVA-2) decode device.

Input data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_crypto_session_input">D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT</a>


Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_crypto_session_output">D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_CURRENT_ENCRYPTION_WHEN_ACCESSIBLE

Returns the encryption type that is applied before content becomes accessible to the CPU or bus.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_accessibility_encryption_guid_count_output">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_DEVICE_HANDLE

Returns a handle to the device that is associated with this authenticated channel.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_device_handle_output">D3D11_1DDI_AUTHENTICATED_QUERY_DEVICE_HANDLE_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID

Returns one of the encryption types that can be used to encrypt content before it becomes accessible to the CPU or bus.

Input data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_accessibility_encryption_guid_input">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT</a>


Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_accessibility_encryption_guid_output">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID_COUNT

Returns the number of encryption types that can be used to encrypt content before it becomes accessible to the CPU or bus.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_accessibility_encryption_guid_count_output">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID

Returns one of the output identifiers that is associated with a specified cryptographic session and Direct3D device.

Input data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output_id_input">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT</a>


Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output_id_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT

Returns the number of output identifiers that are associated with a specified cryptographic session and Direct3D device.

Input data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output_id_count_input">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_INPUT</a>


Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output_id_count_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_PROTECTION

Returns the current protection level for the device.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_protection_output">D3D11_1DDI_AUTHENTICATED_QUERY_PROTECTION_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS

Returns information about a process that is allowed to open shared resources with restricted access.

Input data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_restricted_shared_resource_process_input">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT</a>


Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_restricted_shared_resource_process_output">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_COUNT

Returns the number of processes that are allowed to open shared resources with restricted access.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_restricted_shared_resource_process_count_output">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_COUNT_OUTPUT</a>




#### D3D11_1DDI_AUTHENTICATED_QUERY_UNRESTRICTED_PROTECTED_SHARED_RESOURCE_COUNT

Returns the number of protected shared resources that can be opened by any process with no restrictions.

Output data structure: <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_unrestricted_protected_shared_resource_count_output">D3D11_1DDI_AUTHENTICATED_QUERY_UNRESTRICTED_PROTECTED_SHARED_RESOURCE_COUNT_OUTPUT</a>

### -field hChannel

A handle to the authenticated channel. This handle was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.

### -field SequenceNumber

The query sequence number. At the start of the session, generate a cryptographically secure 32-bit random number to use as the starting sequence number. For each query, increment the sequence number by 1.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a>