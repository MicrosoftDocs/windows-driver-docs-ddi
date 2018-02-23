---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
title: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE is called by the OS to get the size of an OPM certificate.
old-location: display\evt_idd_cx_monitor_opm_get_certificate_size.htm
old-project: display
ms.assetid: f5293625-19eb-4df9-9934-1e1990b7d608
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.evt_idd_cx_monitor_opm_get_certificate_size, EvtIddCxMonitorOpmGetCertificateSize callback function [Display Devices], EvtIddCxMonitorOpmGetCertificateSize, EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE, EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE, iddcx/EvtIddCxMonitorOpmGetCertificateSize, PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback function pointer [Display Devices], PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	iddcx.h
apiname:
-	PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE callback


## -description


<b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b> is called by the OS to get the size of an OPM certificate.


## -prototype


````
EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE EvtIddCxMonitorOpmGetCertificateSize;

NTSTATUS EvtIddCxMonitorOpmGetCertificateSize(
  _In_        IDDCX_ADAPTER                       AdapterObject,
  _In_  const IDARG_IN_OPM_GET_CERTIFICATE_SIZE*  pInArgs,
  _Out_       IDARG_OUT_OPM_GET_CERTIFICATE_SIZE* pOutArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE;
````


## -parameters




### -param AdapterObject [in]


                    
                The object for the adapter that the OPM certificate size will be gotten for.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b>.


### -param pOutArgs [out]


                    
                Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    



