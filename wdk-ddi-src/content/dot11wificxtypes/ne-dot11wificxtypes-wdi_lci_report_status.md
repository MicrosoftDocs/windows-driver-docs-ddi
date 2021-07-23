---
UID: NE:dot11wificxtypes._WDI_LCI_REPORT_STATUS
tech.root: netvista
title: WDI_LCI_REPORT_STATUS (dot11wificxtypes.h)
ms.date: 07/30/2021
targetos: Windows
description: The WDI_LCI_REPORT_STATUS enum defines the response status for an LCI report, if the report were requested in a Fine Timing Measurement (FTM) request.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_LCI_REPORT_STATUS
 - WDI_LCI_REPORT_STATUS
f1_keywords:
 - _WDI_LCI_REPORT_STATUS
 - dot11wificxtypes/_WDI_LCI_REPORT_STATUS
 - WDI_LCI_REPORT_STATUS
 - dot11wificxtypes/WDI_LCI_REPORT_STATUS
dev_langs:
 - c++
---

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

This enumeration is a value in the [WDI_TLV_FTM_RESPONSE](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response) TLV.

## -see-also

[WDI_TLV_FTM_RESPONSE](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response)

[NDIS_STATUS_WDI_INDICATION_REQUEST_FTM_COMPLETE](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-request-ftm-complete)

[OID_WDI_TASK_REQUEST_FTM](/windows-hardware/drivers/netcx/oid-wdi-task-request-ftm)

