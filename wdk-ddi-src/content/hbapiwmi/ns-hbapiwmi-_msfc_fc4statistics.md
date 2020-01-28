---
UID: NS:hbapiwmi._MSFC_FC4STATISTICS
title: _MSFC_FC4STATISTICS (hbapiwmi.h)
description: The MSFC_FC4STATISTICS structure is used in conjunction with the GetFC4Statistics WMI method to report traffic statistics on a port of type Nx_Port for the indicated FC-4 protocol.
old-location: storage\msfc_fc4statistics.htm
tech.root: storage
ms.assetid: a46a9aff-9bc9-4328-85b2-90f8f80b2e65
ms.date: 03/29/2018
ms.keywords: "*PMSFC_FC4STATISTICS, MSFC_FC4STATISTICS, MSFC_FC4STATISTICS structure [Storage Devices], PMSFC_FC4STATISTICS, PMSFC_FC4STATISTICS structure pointer [Storage Devices], _MSFC_FC4STATISTICS, hbapiwmi/MSFC_FC4STATISTICS, hbapiwmi/PMSFC_FC4STATISTICS, storage.msfc_fc4statistics, structs-Fibre_aad92cde-3922-49dd-8473-fefff79e5e2b.xml"
f1_keywords:
 - "hbapiwmi/MSFC_FC4STATISTICS"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- MSFC_FC4STATISTICS
product:
- Windows
targetos: Windows
req.typenames: MSFC_FC4STATISTICS, *PMSFC_FC4STATISTICS
---

# _MSFC_FC4STATISTICS structure


## -description


The MSFC_FC4STATISTICS structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a> WMI method to report traffic statistics on a port of type Nx_Port for the indicated FC-4 protocol.


## -struct-fields




### -field InputRequests

Indicates the number of input requests.


### -field OutputRequests

Indicates the number of output requests.


### -field ControlRequests

Indicates the number of control requests.


### -field InputMegabytes

Indicates the number of megabytes of data that has been input.


### -field OutputMegabytes

Indicates the number of megabytes of data that has been output.


## -remarks



The statistics counters whose values are reported in the members of this structure are 64-bit signed integers that wrap to zero on exceeding 2**63-1. The statistics counters are not reset during normal operation, so traffic rates may be determined by the difference of counter values derived from two successive calls, with appropriate adjustments to for counter wrap.

If an HBA does not support a specific statistic, it shall return the value of -1 for corresponding counter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_getfc4statistics_in">GetFC4Statistics_IN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_getfc4statistics_out">GetFC4Statistics_OUT</a>
 

 

