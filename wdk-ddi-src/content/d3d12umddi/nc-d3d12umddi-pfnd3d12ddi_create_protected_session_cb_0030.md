---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
title: PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
author: windows-driver-content
description: Used to create a protected session state.
old-location: display\pfnd3d12ddi_create_protected_session_cb_0030.htm
old-project: display
ms.assetid: 64E38759-2863-4481-8A89-6E6263CEFE8B
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_create_protected_session_cb_0030, PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function [Display Devices], PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030, d3d12umddi/PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback


## -description


Used to create a protected session state.


## -prototype


````
HRESULT APIENTRY CALLBACK* PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030(
       D3D12DDI_HRTDEVICE                hRTDevice,
       D3D12DDI_HRTPROTECTEDSESSION_0030 hRTProtectedSession,
  _In_ pArgs                             *D3D12DDICB_CREATE_PROTECTED_RESOURCE_SESSION
);
````


## -parameters




### -param hRTDevice

The hardware device being processed.


### -param hRTProtectedSession

The protected session.


### -param *pArgs








#### - D3D12DDICB_CREATE_PROTECTED_RESOURCE_SESSION [in]

Used to create a protected resource session


## -returns



Returns STATUS_SUCCESS if completed successfully.



