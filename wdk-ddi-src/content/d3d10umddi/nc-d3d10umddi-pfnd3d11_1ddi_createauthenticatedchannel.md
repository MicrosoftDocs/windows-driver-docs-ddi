---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL (d3d10umddi.h)
description: Creates an authenticated channel object. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.
old-location: display\createauthenticatedchannel1.htm
ms.assetid: 90b43bc3-6569-4799-8be3-e4e60f59164f
ms.date: 05/10/2018
ms.keywords: CreateAuthenticatedChannel, CreateAuthenticatedChannel callback function [Display Devices], PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL, PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL callback, d3d10umddi/CreateAuthenticatedChannel, display.createauthenticatedchannel1
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- CreateAuthenticatedChannel
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEAUTHENTICATEDCHANNEL callback function


## -description


Creates an authenticated channel object. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCreateData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406306">D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure. This structure specifies the attributes of the authenticated channel to be created.


### -param hAuthChannel [in]

A handle to the driver's private data for the authenticated channel object. For more information, see the Remarks section.


### -param hRTAuthChannel [in]

A handle to the authenticated channel object that the driver should use when it calls back into the Direct3D runtime.


## -returns



Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The authenticated channel was created successfully. | 
| **D3DDDIERR_DEVICEREMOVED** | The graphics adapter was removed. | 
| **E_OUTOFMEMORY** | Memory was not available to complete the operation. | 


## -remarks



The Direct3D runtime calls <i>CreateAuthenticatedChannel(D3D11_1)</i> after it has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451604">CalcPrivateAuthenticatedChannelSize</a> to determine the size in bytes for the private data that the driver requires for the authenticated channel object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the authentication channel object.

When the runtime  calls <i>CreateAuthenticatedChannel(D3D11_1)</i>, it passes the handle to the private data memory in the <i>hAuthChannel</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the authenticated channel. The driver should fail all subsequent calls that use this created authenticated channel, such as <a href="https://msdn.microsoft.com/library/windows/hardware/hh451691">NegotiateAuthenticatedChannelKeyExchange</a>, if the display device that is specified in those calls is different from the display device that was used to create the authenticated channel. 






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451604">CalcPrivateAuthenticatedChannelSize</a>



<a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406306">D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451691">NegotiateAuthenticatedChannelKeyExchange</a>
 

 

