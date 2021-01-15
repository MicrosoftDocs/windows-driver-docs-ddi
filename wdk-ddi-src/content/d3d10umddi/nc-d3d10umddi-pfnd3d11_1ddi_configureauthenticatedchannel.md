---
UID: NC:d3d10umddi.PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL (d3d10umddi.h)
description: Processes a request from an application to configure an authenticated channel for content protection. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.
old-location: display\configureauthenticatedchannel1.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL callback function"]
ms.keywords: ConfigureAuthenticatedChannel, ConfigureAuthenticatedChannel callback function [Display Devices], PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL, PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL callback, d3d10umddi/ConfigureAuthenticatedChannel, display.configureauthenticatedchannel1
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
 - d3d10umddi/PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
product:
 - Windows
---

# PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL callback function


## -description

Processes  a request from an application to configure an authenticated channel for content protection. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCAuthChannel

A handle to the authenticated channel object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.

### -param InputDataSize

The size, in bytes, of the array that is specified by the <i>pInputData</i> parameter.

### -param pInputData

A pointer to a byte array that contains input data for the command. For more information, see the Remarks section.

### -param pOutputData

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a> structure. For more information, see the Remarks section.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The authenticated channel was configured successfully. | 
| **E_FAIL** | The display miniport driver does not support the specified command | 
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. | 
| **E_OUTOFMEMORY** |     Memory was not available to complete the operation. |

## -remarks

The byte array that is referenced by the <i>pInputData</i> parameter is formatted in the following way:

* This array starts with a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure. 

* The data that follows this structure is in a format that is specified by the <b>ConfigureType</b> member of the structure. 

The following list describes the format of this data based on the <b>ConfigureType</b> member. 

* **D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID**
<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>

* **D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID**
<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>


* **D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID**
<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>

* **D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID**
<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>

* **D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID**
<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>


The <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure contains an AES-based one-key CBC message authentication code (OMAC) of the data. The display miniport driver must calculate its own OMAC over the data to authenticate the data. This input structure also contains a driver handle to the authenticated channel, a sequence number, and a GUID that indicates the configuration type.



The display miniport driver follows these steps when it initializes the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a> structure:

1. The driver must copy the input data to the [D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT](./ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output.md)  structure.

2. The driver must set the ReturnCode member to the same return code that it will return for the ConfigureAuthenticatedChannel(D3D11_1) call. This provides the application with a secure mechanism of accessing the return code.

3. The driver sets the omac member to zero and then calculates an OMAC for the data in the structure. The driver then sets the omac member to the OMAC that it calculated

The display miniport driver must return  <b>E_INVALIDARG</b> for the <b>ConfigureAuthenticatedChannel</b> call under the following conditions:

* The omac member of the[D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT](./ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md)  structure does not match the OMAC that the driver calculated.

* The sequence number is not greater than a sequence number that was specified in a previous configuration call.

* The sequence number has not yet been initialized by a call to the ConfigureAuthenticatedChannel(D3D11_1) function.

* The InputDataSize parameter is less than the size of the [D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT](./ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md)  structure plus the size of the structure specified by the D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureTypemember.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a>

