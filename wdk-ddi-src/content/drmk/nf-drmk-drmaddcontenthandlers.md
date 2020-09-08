---
UID: NF:drmk.DrmAddContentHandlers
title: DrmAddContentHandlers function (drmk.h)
description: The DrmAddContentHandlers function provides the system with a list of functions that handle protected content.
old-location: audio\drmaddcontenthandlers.htm
tech.root: audio
ms.assetid: da2ec371-052a-4ea1-9336-9e32df936227
ms.date: 05/08/2018
keywords: ["DrmAddContentHandlers function"]
ms.keywords: DrmAddContentHandlers, DrmAddContentHandlers function [Audio Devices], aud-prop2_94f530fb-9766-4d61-a002-b1c7bd5183d5.xml, audio.drmaddcontenthandlers, drmk/DrmAddContentHandlers
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
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
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DrmAddContentHandlers
 - drmk/DrmAddContentHandlers
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Drmk.lib
 - Drmk.dll
api_name:
 - DrmAddContentHandlers
---

# DrmAddContentHandlers function


## -description

The <code>DrmAddContentHandlers</code> function provides the system with a list of functions that handle protected content.

## -parameters

### -param ContentId 

[in]
Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

### -param paHandlers 

[in]
Pointer to an array of function pointers. Each array element points to a content handler.

### -param NumHandlers 

[in]
Specifies the number of function pointers in the <i>paHandlers</i> array.

## -returns

<code>DrmAddContentHandlers</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

Before allowing protected content to flow through a data path, the system verifies that the data path is secure. To do so, the system authenticates each module in the data path beginning at the upstream end of the data path and moving downstream. As each module is authenticated, that module gives the system information about the next module in the data path so that it can also be authenticated. To be successfully authenticated, a module's binary file must be signed as DRM-compliant.

If two adjacent modules communicate with each other through either the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a> function or the downstream module's COM interface, the upstream module calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a> function, respectively, to provide the system with information about the downstream module. However, if the two modules use any other type of interface to communicate, the upstream module calls the <code>DrmAddContentHandlers</code> function instead.

The <i>paHandlers</i> array contains function pointers to entry points in the downstream module. <code>DrmAddContentHandlers</code> authenticates the module that implements these functions. (If the entry points are distributed among several modules, the function authenticates all these modules.) The vendor-defined functions in this array make up an interface that is understood by both the module that calls the functions and the module that implements the functions. <code>DrmAddContentHandlers</code> does not directly call any of these functions.

The upstream module can pass both the content ID and content rights to the downstream module by using one of the functions in the <i>paHandlers</i> array for this purpose. The downstream module needs the content ID to advise the system of any modules to which it sends the protected content.

<i>DrmAddContentHandlers</i> performs the same function as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcaddcontenthandlers">PcAddContentHandlers</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-idrmport2-addcontenthandlers">IDrmPort2::AddContentHandlers</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/drm-functions-and-interfaces">DRM Functions and Interfaces</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-idrmport2-addcontenthandlers">IDrmPort2::AddContentHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcaddcontenthandlers">PcAddContentHandlers</a>

