---
UID: NF:iddcx.IddCxAdapterUpdateMaxDisplayPipelineRate
title: IddCxAdapterUpdateMaxDisplayPipelineRate function
author: windows-driver-content
description: An OS callback function the driver calls to report that the max display pipeline rate has changed.
old-location: display\iddcxadapterupdatemaxdisplaypipelinerate.htm
tech.root: display
ms.assetid: 5d8e6b87-6cfd-48ec-ac38-a75cb94cf5ac
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: IddCxAdapterUpdateMaxDisplayPipelineRate, IddCxAdapterUpdateMaxDisplayPipelineRate method [Display Devices], display.iddcxadapterupdatemaxdisplaypipelinerate, iddcx/IddCxAdapterUpdateMaxDisplayPipelineRate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: 
req.dll: 
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IddCxAdapterUpdateMaxDisplayPipelineRate
product:
- Windows
targetos: Windows
req.typenames: 
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




(NTSTATUS) The method returns S_OK if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



