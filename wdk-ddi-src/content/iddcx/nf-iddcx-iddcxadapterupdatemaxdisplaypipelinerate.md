---
UID: NF:iddcx.IddCxAdapterUpdateMaxDisplayPipelineRate
title: IddCxAdapterUpdateMaxDisplayPipelineRate function (iddcx.h)
description: An OS callback function the driver calls to report that the max display pipeline rate has changed.
old-location: display\iddcxadapterupdatemaxdisplaypipelinerate.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IddCxAdapterUpdateMaxDisplayPipelineRate function"]
ms.keywords: IddCxAdapterUpdateMaxDisplayPipelineRate, IddCxAdapterUpdateMaxDisplayPipelineRate method [Display Devices], display.iddcxadapterupdatemaxdisplaypipelinerate, iddcx/IddCxAdapterUpdateMaxDisplayPipelineRate
req.header: iddcx.h
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
req.lib: IddCxStub.lib
req.dll: IddCx.dll
req.irql: _Must_inspect_result_
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxAdapterUpdateMaxDisplayPipelineRate
 - iddcx/IddCxAdapterUpdateMaxDisplayPipelineRate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxAdapterUpdateMaxDisplayPipelineRate
---

# IddCxAdapterUpdateMaxDisplayPipelineRate function


## -description

                An OS callback function the driver calls to report that the max display pipeline rate has changed

## -parameters

### -param hOsAdapterContext [in]


This is the OS context handle for this adapter returned by the <b>IddCxStart</b> call

### -param pInArgs [in]


Input arguments to the function

## -returns

(NTSTATUS) The method returns S_OK if the operation succeeds. Otherwise, this method may return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
