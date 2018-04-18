---
UID: NC:wdm.FPGA_BUS_SCAN
title: FPGA_BUS_SCAN
author: windows-driver-content
description: Reserved for future use. Triggers a bus scan at the parent of the FPGA device.
ms.assetid: 9508f992-23b7-49d8-8eb7-3bd5214a6835
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll: 
req.irql: DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	wdm.h
apiname: 
-	FPGA_BUS_SCAN
product: Windows
targetos: Windows
---

# FPGA_BUS_SCAN callback function

## -description
Reserved for future use.

Triggers a bus scan at the parent of the FPGA device.

## -prototype

```
//Declaration

FPGA_BUS_SCAN FpgaBusScan; 

// Definition

VOID FpgaBusScan 
(
	PVOID Context
)
{...}

FPGA_BUS_SCAN *PFPGA_BUS_SCAN


```

## -parameters

### -param Context
[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the bus extension.


## -returns


## -remarks

A device driver that successfully queries for the GUID_PCI_FPGA_CONTROL_INTERFACE interface receives a pointer to a [**FPGA_CONTROL_INTERFACE**](ns-wdm-_fpga_control_interface.md) structure in which the the driver sets the **BusScan** member to a pointer to its implementation of the _FPGA_BUS_SCAN_ callback function.


## -see-also