---
UID: NC:d3dkmddi.DXGKDDI_CREATEPROTECTEDSESSION
title: DXGKDDI_CREATEPROTECTEDSESSION
author: windows-driver-content
description: Used to create a protected session.
old-location: display\dxgkddi_createprotectedsession.htm
ms.assetid: 0FAE7AA0-839D-4D21-BC10-46B2B651979F
ms.date: 5/10/2018
ms.keywords: DXGKDDI_CREATEPROTECTEDSESSION, DXGKDDI_CREATEPROTECTEDSESSION callback, DXGKDDI_CREATEPROTECTEDSESSION callback function [Display Devices], d3dkmddi/DXGKDDI_CREATEPROTECTEDSESSION, display.dxgkddi_createprotectedsession
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: requires_(PASSIVE_LEVEL)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DXGKDDI_CREATEPROTECTEDSESSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_CREATEPROTECTEDSESSION callback function


## -description


Used to create a protected session.


## -parameters




### -param hAdapter [in]

A handle to the adapter.


### -param pCreateProtectedSession [in, out]

A pointer to the arguments used to create a protected session.


## -returns



Returns STATUS_SUCCESS if completed successfully.



