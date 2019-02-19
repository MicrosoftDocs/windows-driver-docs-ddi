---
UID: NE:wditypes._WDI_LCI_REPORT_STATUS
title: WDI_LCI_REPORT_STATUS
author: windows-driver-content
description: The WDI_LCI_REPORT_STATUS enumeration defines the response status for an LCI report, if the report were requested in a Fine Timing Measurement (FTM) request.
tech.root: netvista
ms.assetid: 2e552374-3964-49e4-9fc1-3befeebaced1
ms.author: windowsdriverdev
ms.date: 02/13/2019
ms.topic: enum
ms.keywords: WDI_LCI_REPORT_STATUS, WDI_LCI_REPORT_STATUS, 
req.header: wditypes.hpp
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WDI_LCI_REPORT_STATUS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wditypes.hpp
api_name: 
 - WDI_LCI_REPORT_STATUS
product:
- Windows
targetos: Windows
---

# WDI_LCI_REPORT_STATUS enumeration

## -description

The **WDI_LCI_REPORT_STATUS** enumeration defines the response status for an LCI report, if the report were requested in a Fine Timing Measurement (FTM) request.

## -enum-fields

### -field WDI_LCI_REPORT_STATUS_SUCCESS 

The LCI report was successfully obtained.

### -field WDI_LCI_REPORT_STATUS_FAILURE 

A failure occurred while getting the report.

### -field WDI_LCI_REPORT_STATUS_INCAPABLE 

The **Incapable** bit of the Measurement Report Mode field is set. For more info, see section 9.4.2.22, the Measurement Report element, of the [802-11-2016 standard](https://standards.ieee.org/standard/802_11-2016.html).

### -field WDI_LCI_REPORT_STATUS_REFUSED 

The **Refused** bit of the Measurement Report Mode field is set. For more info, see section 9.4.2.22, the Measurement Report element, of the [802-11-2016 standard](https://standards.ieee.org/standard/802_11-2016.html).

## -remarks

This enumeration is a value in the [WDI_TLV_FTM_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/wdi-tlv-ftm-response) TLV.

## -see-also

[WDI_TLV_FTM_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/wdi-tlv-ftm-response)

[NDIS_STATUS_WDI_INDICATION_REQUEST_FTM_COMPLETE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wdi-indication-request-ftm-complete)

[OID_WDI_TASK_REQUEST_FTM](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wdi-task-request-ftm)