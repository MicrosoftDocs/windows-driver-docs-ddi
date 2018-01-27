---
UID: NC:pcivirt.SRIOV_QUERY_PROBED_BARS
title: SRIOV_QUERY_PROBED_BARS
author: windows-driver-content
description: Queries the data read from the physical function's (PF) base address registers (BARs) if the value -1 were written to them first.
old-location: pci\sriov_query_probed_bars.htm
old-project: PCI
ms.assetid: 422a9212-7227-4508-8f06-0056349fa835
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.sriov_query_probed_bars, SriovQueryProbedBars callback function [Buses], SriovQueryProbedBars, SRIOV_QUERY_PROBED_BARS, SRIOV_QUERY_PROBED_BARS, pcivirt/SriovQueryProbedBars, *PSRIOV_QUERY_PROBED_BARS callback function pointer [Buses], *PSRIOV_QUERY_PROBED_BARS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pcivirt.h
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Pcivirt.h
apiname: 
-	*PSRIOV_QUERY_PROBED_BARS
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_PROBED_BARS callback


## -description



Queries the data read from
    the physical  function's (PF) base address registers (BARs) if the value -1 were written to them first.


## -prototype


````
SRIOV_QUERY_PROBED_BARS SriovQueryProbedBars;

NTSTATUS SriovQueryProbedBars(
  _In_  PVOID  Context,
  _Out_ PULONG BaseRegisterValues
)
{ ... }

typedef SRIOV_QUERY_PROBED_BARS *PSRIOV_QUERY_PROBED_BARS;
````


## -parameters




### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param BaseRegisterValues [out]

A pointer to an array of variables that is bounded by the number of BARs in a PCI device.


## -returns



Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.



## -remarks


This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get base address register values. 

The PF driver registers its implementation by setting the <b>QueryProbedBars</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.


