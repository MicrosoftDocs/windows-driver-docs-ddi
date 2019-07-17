---
UID: NF:sercx.SERCX2_CONFIG_INIT
title: SERCX2_CONFIG_INIT function (sercx.h)
description: The SERCX2_CONFIG_INIT function initializes a SERCX2_CONFIG structure.
old-location: serports\sercx2_config_init.htm
tech.root: serports
ms.assetid: 630C7EDA-8C6A-4BD7-9287-EA15FBA34408
ms.date: 04/23/2018
ms.keywords: 2/SERCX2_CONFIG_INIT, SERCX2_CONFIG_INIT, SERCX2_CONFIG_INIT function [Serial Ports], serports.sercx2_config_init
ms.topic: function
f1_keywords:
 - "sercx/SERCX2_CONFIG_INIT"
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Any level.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 2.0\Sercx.h
api_name:
- SERCX2_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SERCX2_CONFIG_INIT function


## -description


The <b>SERCX2_CONFIG_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2ApplyConfig [in]

The value to load into the <b>EvtSerCx2ApplyConfig</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a>.


### -param EvtSerCx2Control [in]

The value to load into the <b>EvtSerCx2Control</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a>.


### -param EvtSerCx2PurgeFifos [in]

The value to load into the <b>EvtSerCx2PurgeFifos</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a>.


## -returns



None.




## -remarks



Your serial controller driver must use this function to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method.

<b>SERCX2_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_CONFIG_INIT</b> call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>
 

 

