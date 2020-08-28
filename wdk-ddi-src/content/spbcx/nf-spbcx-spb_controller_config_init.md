---
UID: NF:spbcx.SPB_CONTROLLER_CONFIG_INIT
title: SPB_CONTROLLER_CONFIG_INIT function (spbcx.h)
description: The SPB_CONTROLLER_CONFIG_INIT function initializes an SPB_CONTROLLER_CONFIG structure.
old-location: spb\spb_controller_config_init.htm
tech.root: SPB
ms.assetid: 78D46903-A13D-4BC2-803F-E1656A43E865
ms.date: 04/30/2018
keywords: ["SPB_CONTROLLER_CONFIG_INIT function"]
ms.keywords: SPB.spb_controller_config_init, SPB_CONTROLLER_CONFIG_INIT, SPB_CONTROLLER_CONFIG_INIT function [Buses], spbcx/SPB_CONTROLLER_CONFIG_INIT
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
 - SPB_CONTROLLER_CONFIG_INIT
 - spbcx/SPB_CONTROLLER_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spbcx.h
api_name:
 - SPB_CONTROLLER_CONFIG_INIT
---

# SPB_CONTROLLER_CONFIG_INIT function


## -description

The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
A pointer to the <b>SPB_CONTROLLER_CONFIG</b> structure that is to be initialized.

## -remarks

Your SPB controller driver must use this function to initialize an <b>SPB_CONTROLLER_CONFIG</b> structure before passing this structure as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method. This method completes the initialization of the SPB framework extension (SpbCx).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>

