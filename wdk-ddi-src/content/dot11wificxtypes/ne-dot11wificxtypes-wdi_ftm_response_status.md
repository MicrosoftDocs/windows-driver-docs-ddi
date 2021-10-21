---
UID: NE:dot11wificxtypes._WDI_FTM_RESPONSE_STATUS
tech.root: netvista
title: WDI_FTM_RESPONSE_STATUS (dot11wificxtypes.h)
ms.date: 09/15/2021
targetos: Windows
description: The WDI_FTM_RESPONSE_STATUS enum defines the response status for a Fine Timing Measurement (FTM) request.
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
 - _WDI_FTM_RESPONSE_STATUS
 - WDI_FTM_RESPONSE_STATUS
f1_keywords:
 - _WDI_FTM_RESPONSE_STATUS
 - dot11wificxtypes/_WDI_FTM_RESPONSE_STATUS
 - WDI_FTM_RESPONSE_STATUS
 - dot11wificxtypes/WDI_FTM_RESPONSE_STATUS
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_FTM_RESPONSE_STATUS** enumeration defines the response status for a Fine Timing Measurement (FTM) request.

## -enum-fields

### -field WDI_FTM_RESPONSE_STATUS_SUCCESS:0 

The FTM was a success.

### -field WDI_FTM_RESPONSE_STATUS_UNREACHABLE:1

No ACK was received for the FTM request from the target, or no first FTM frame was received afterwards. The application will be advised to first trigger a new scan before retrying.

### -field WDI_FTM_RESPONSE_STATUS_REJECTED:2

The status indication field from Table 9-256 of the [802-11-2016 standard](https://standards.ieee.org/standard/802_11-2016.html) was set to **3**. A **RetryValue** should be provided and the application will be advised to retry only after that time has passed.

### -field WDI_FTM_RESPONSE_STATUS_INCAPABLE:3

The status indication field from Table 9-256 of the [802-11-2016 standard](https://standards.ieee.org/standard/802_11-2016.html) was set to **2**. The application will be advised not to retry.

### -field WDI_FTM_RESPONSE_STATUS_TIMEOUT:4

The FTM session was started but it did not complete before the timeout expired. A retry to this STA might work.

### -field WDI_FTM_RESPONSE_STATUS_NOT_ATTEMPTED:5

The FTM session was not initiated. It is highly likely that a retry to this STA will work.

### -field WDI_FTM_RESPONSE_STATUS_ABORTED:6

The FTM procedure did not complete because the task was aborted. It is likely that a retry to this STA will work.

### -field WDI_FTM_RESPONSE_STATUS_FAILED:7

The FTM procedure failed with any other failure besides the preceding failure responses. A retry to this STA might or might not work.

## -remarks

This enumeration is a value in the [WDI_TLV_FTM_RESPONSE](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response) TLV.

## -see-also

[WDI_TLV_FTM_RESPONSE](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response)

[NDIS_STATUS_WDI_INDICATION_REQUEST_FTM_COMPLETE](/windows-hardware/drivers/netcx/ndis-status-wdi-indication-request-ftm-complete)

[OID_WDI_TASK_REQUEST_FTM](/windows-hardware/drivers/netcx/oid-wdi-task-request-ftm)
