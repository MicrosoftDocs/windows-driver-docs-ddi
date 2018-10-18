---
UID: NC:pcivirt.SRIOV_RESET_FUNCTION
title: SRIOV_RESET_FUNCTION
author: windows-driver-content
description: Resets the specified PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_reset_function.htm
tech.root: PCI
ms.assetid: 30c01528-8254-431f-aaba-79c05f66fc00
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_RESET_FUNCTION, *PSRIOV_RESET_FUNCTION callback function pointer [Buses], PCI.sriov_reset_function, SRIOV_RESET_FUNCTION, SriovResetFunction, SriovResetFunction callback function [Buses], pcivirt/SriovResetFunction"
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
-	*PSRIOV_RESET_FUNCTION
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_RESET_FUNCTION callback


## -description


Resets the specified PCI Express SR-IOV Virtual Function (VF).


## -prototype


```cpp
SRIOV_RESET_FUNCTION SriovResetFunction;

NTSTATUS SriovResetFunction(
  _In_ PVOID  Context,
  _In_ USHORT VfIndex
)
{ ... }

typedef SRIOV_RESET_FUNCTION *PSRIOV_RESET_FUNCTION;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param VfIndex [in]

A zero-based index of the VF that is to be reset.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to reset a specific virtual function.

The PF driver registers its implementation by setting the <b>ResetVf </b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



