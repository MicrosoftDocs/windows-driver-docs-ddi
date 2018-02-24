---
UID: NC:pcivirt.SRIOV_QUERY_PROBED_BARS_2
title: SRIOV_QUERY_PROBED_BARS_2
author: windows-driver-content
description: Queries the data read from the specified PCI Express SR-IOV Virtual Function (VF) base address registers (BARs) if the value -1 were written to them first.
old-location: pci\sriov_query_probed_bars_2.htm
old-project: PCI
ms.assetid: e0c079aa-8adf-42c9-a4ac-bfc623471964
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PCI.sriov_query_probed_bars_2, SriovQueryProbedBars2 callback function [Buses], SriovQueryProbedBars2, SRIOV_QUERY_PROBED_BARS_2, SRIOV_QUERY_PROBED_BARS_2, pcivirt/SriovQueryProbedBars2, *PSRIOV_QUERY_PROBED_BARS_2 callback function pointer [Buses], *PSRIOV_QUERY_PROBED_BARS_2
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
-	*PSRIOV_QUERY_PROBED_BARS_2
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_PROBED_BARS_2 callback


## -description



Queries the data read from
    the specified PCI Express SR-IOV Virtual Function (VF) base address registers (BARs) if the value -1 were written to them first.


## -prototype


````
SRIOV_QUERY_PROBED_BARS_2 SriovQueryProbedBars2;

NTSTATUS SriovQueryProbedBars2(
  _In_  PVOID  Context,
  _In_  USHORT VfIndex,
  _Out_ PULONG BaseRegisterValues
)
{ ... }

typedef SRIOV_QUERY_PROBED_BARS_2 *PSRIOV_QUERY_PROBED_BARS_2;
````


## -parameters




### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param VfIndex [in]

A zero-based index of the VF that is being queried. 


### -param BaseRegisterValues [out]

A pointer to an array of variables that is bounded by the number of BARs in a PCI device.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read from
    the specified virtual function's (VF) base address registers. 

The PF driver registers its implementation by setting the <b>QueryProbedBars_2</b> member of the <a href="https://msdn.microsoft.com/46c9fa94-283c-481e-9fb1-2ed63df00386">SRIOV_DEVICE_INTERFACE_STANDARD_2</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

This callback is invoked by the virtualization stack (non-privileged) when it wants to find out the VF’s base address register values after the registers are written with the value (-1).  This process is conventional when setting up a PCI device, and the result allows the PCI driver to know the amount of address space that would be decoded by the device after it is enabled.  When a non-privileged VM writes to the VF’s BARs, the privileged VM can stop functioning. Therefore, this routine requires the need for writing to the BARs.



