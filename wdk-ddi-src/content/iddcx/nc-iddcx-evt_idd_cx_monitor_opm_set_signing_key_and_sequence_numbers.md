---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
title: EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS is called by the OS to set the signing key and sequence number.
old-location: display\evt_idd_cx_monitor_opm_set_signing_key_and_sequence_numbers.htm
old-project: display
ms.assetid: 98a874e7-4eea-4b35-833f-60f49ea5f599
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.evt_idd_cx_monitor_opm_set_signing_key_and_sequence_numbers, EvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers callback function [Display Devices], EvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers, EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, iddcx/EvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers, PFN_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback function pointer [Display Devices], PFN_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
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
req.irql: _requires_same_
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	iddcx.h
apiname: 
-	PFN_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback


## -description


<b>EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS</b> is called by the OS to set the signing key and sequence number.


## -prototype


````
EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS EvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers;

NTSTATUS EvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers(
  _In_       IDDCX_OPMCTX                                       OpmCxtObject,
  _In_ const IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS* pInArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS PFN_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS;
````


## -parameters




### -param OpmCxtObject [in]


                    
                The object for the OPM context whose signing key and sequence number will be set.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS</b>.


## -returns



(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    


