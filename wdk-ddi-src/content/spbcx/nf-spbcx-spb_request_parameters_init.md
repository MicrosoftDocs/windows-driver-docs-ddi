---
UID: NF:spbcx.SPB_REQUEST_PARAMETERS_INIT
title: SPB_REQUEST_PARAMETERS_INIT function (spbcx.h)
description: The SPB_REQUEST_PARAMETERS_INIT function initializes an SPB_REQUEST_PARAMETERS structure.
old-location: spb\spb_request_parameters_init.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SPB_REQUEST_PARAMETERS_INIT function"]
ms.keywords: SPB.spb_request_parameters_init, SPB_REQUEST_PARAMETERS_INIT, SPB_REQUEST_PARAMETERS_INIT function [Buses], spbcx/SPB_REQUEST_PARAMETERS_INIT
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Any IRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - SPB_REQUEST_PARAMETERS_INIT
 - spbcx/SPB_REQUEST_PARAMETERS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spbcx.h
api_name:
 - SPB_REQUEST_PARAMETERS_INIT
---

# SPB_REQUEST_PARAMETERS_INIT function


## -description

The <b>SPB_REQUEST_PARAMETERS_INIT</b> function initializes an <a href="/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a> structure.

## -parameters

### -param Parameters 

[out]
A pointer to the <b>SPB_REQUEST_PARAMETERS</b> structure that is to be initialized.

## -remarks

Your SPB controller driver must use this function to initialize an <b>SPB_REQUEST_PARAMETERS</b> structure before passing this structure as an output parameter to the <a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a> method. This method writes the SPB-specific parameters from an I/O request to this structure.

## -see-also

<a href="/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a>
