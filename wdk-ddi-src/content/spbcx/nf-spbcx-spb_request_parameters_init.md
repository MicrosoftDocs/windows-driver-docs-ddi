---
UID: NF:spbcx.SPB_REQUEST_PARAMETERS_INIT
title: SPB_REQUEST_PARAMETERS_INIT function (spbcx.h)
description: The SPB_REQUEST_PARAMETERS_INIT function initializes an SPB_REQUEST_PARAMETERS structure.
old-location: spb\spb_request_parameters_init.htm
tech.root: SPB
ms.assetid: 65C3DF3D-812D-44ED-B471-2D29ADBC2BBA
ms.date: 04/30/2018
ms.keywords: SPB.spb_request_parameters_init, SPB_REQUEST_PARAMETERS_INIT, SPB_REQUEST_PARAMETERS_INIT function [Buses], spbcx/SPB_REQUEST_PARAMETERS_INIT
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Spbcx.h
api_name:
- SPB_REQUEST_PARAMETERS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SPB_REQUEST_PARAMETERS_INIT function


## -description


The <b>SPB_REQUEST_PARAMETERS_INIT</b> function initializes an <a href="https://docs.microsoft.com/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a> structure.


## -parameters




### -param Parameters [out]

A pointer to the <b>SPB_REQUEST_PARAMETERS</b> structure that is to be initialized.


## -returns



None.




## -remarks



Your SPB controller driver must use this function to initialize an <b>SPB_REQUEST_PARAMETERS</b> structure before passing this structure as an output parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a> method. This method writes the SPB-specific parameters from an I/O request to this structure.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/hh406209(v=vs.85)">SPB_REQUEST_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a>
 

 

