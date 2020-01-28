---
UID: NF:wdfdpc.WDF_DPC_CONFIG_INIT
title: WDF_DPC_CONFIG_INIT function (wdfdpc.h)
description: The WDF_DPC_CONFIG_INIT function initializes a driver's WDF_DPC_CONFIG structure.
old-location: wdf\wdf_dpc_config_init.htm
tech.root: wdf
ms.assetid: 12b34b79-0154-4b25-83e7-b15642154b05
ms.date: 02/26/2018
ms.keywords: DFDpcObjectRef_ba15c593-3f2a-4e7f-9a58-a550ca47ccc1.xml, WDF_DPC_CONFIG_INIT, WDF_DPC_CONFIG_INIT function, kmdf.wdf_dpc_config_init, wdf.wdf_dpc_config_init, wdfdpc/WDF_DPC_CONFIG_INIT
f1_keywords:
 - "wdfdpc/WDF_DPC_CONFIG_INIT"
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdpc.h
api_name:
- WDF_DPC_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DPC_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DPC_CONFIG_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a> structure.


### -param EvtDpcFunc [in]

A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function.


## -remarks



The <b>WDF_DPC_CONFIG_INIT</b> function stores the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> pointer and sets the <b>AutomaticSerialization</b> member of the WDF_DPC_CONFIG structure to <b>TRUE</b>.


#### Examples

For a code example that uses the <b>WDF_DPC_CONFIG_INIT</b> function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a>
 

 

