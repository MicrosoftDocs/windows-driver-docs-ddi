---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_INIT_FINISHED
title: EVT_IDD_CX_ADAPTER_INIT_FINISHED
author: windows-driver-content
description: EVT_IDD_CX_ADAPTER_INIT_FINISHED is called by the OS to inform the driver that the adapter initialization has completed.
old-location: display\evt_idd_cx_adapter_init_finished.htm
old-project: display
ms.assetid: cbce9e1b-2f84-4653-8d3d-e5243a1f0eee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WcsTranslateColors
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_IDD_CX_ADAPTER_INIT_FINISHED
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_ADAPTER_INIT_FINISHED callback



## -description
<b>EVT_IDD_CX_ADAPTER_INIT_FINISHED</b> is called by the OS to inform the driver that the adapter initialization has completed.



## -prototype

````
EVT_IDD_CX_ADAPTER_INIT_FINISHED EvtIddCxAdapterInitFinished;

NTSTATUS EvtIddCxAdapterInitFinished(
  _In_       IDDCX_ADAPTER AdapterObject,
  _In_ const               pInArgs
)
{ ... }

typedef EVT_IDD_CX_ADAPTER_INIT_FINISHED PFN_IDD_CX_ADAPTER_INIT_FINISHED;
````


## -parameters

### -param AdapterObject [in]


                    
                A handle provided by the driver used by the OS to reference the adapter in a call to the driver.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_ADAPTER_COMMIT_MODES</b>.


## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    


## -remarks
