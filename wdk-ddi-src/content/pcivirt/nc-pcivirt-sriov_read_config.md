---
UID: NC:pcivirt.SRIOV_READ_CONFIG
title: SRIOV_READ_CONFIG
author: windows-driver-content
description: Reads data from the configuration space of the specified PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_read_config.htm
tech.root: PCI
ms.assetid: 0fef9d53-b8af-4c9b-9914-982bcfc26517
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_READ_CONFIG, *PSRIOV_READ_CONFIG callback function [Buses], PCI.sriov_read_config, SRIOV_READ_CONFIG, SRIOV_READ_CONFIG callback function [Buses], pcivirt/SRIOV_READ_CONFIG"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Pcivirt.h
api_name:
-	*PSRIOV_READ_CONFIG
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_READ_CONFIG callback


## -description


Reads data from  the configuration space of the specified PCI Express SR-IOV Virtual Function (VF).


## -prototype


```
NTSTATUS  SRIOV_READ_CONFIG(
  _In_        PVOID  Context,
  _Out_ const VOID   *Data,
  _In_        USHORT VfIndex,
  _In_        ULONG  Offset,
  _In_        ULONG  Length
);

typedef SRIOV_READ_CONFIG *PSRIOV_READ_CONFIG;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param Data [out]

A pointer to buffer that contains the configuration information to be read from the VF's configuration space.


### -param VfIndex [in]

A zero-based index of the VF to which this read operation applies.


### -param Offset [in]

An offset in bytes to the start of the VF’s configuration space where the read begins.


### -param Length [in]

The length, in bytes, of the data to read from the configuration space.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read from the configuration space of a specific virtual function.

The PF driver registers its implementation by setting the <b>ReadVfConfig</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



