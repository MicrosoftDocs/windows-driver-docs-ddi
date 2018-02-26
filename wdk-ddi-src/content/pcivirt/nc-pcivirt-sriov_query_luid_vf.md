---
UID: NC:pcivirt.SRIOV_QUERY_LUID_VF
title: SRIOV_QUERY_LUID_VF
author: windows-driver-content
description: Gets the PCI Express SR-IOV Virtual Function (VF) given a unique identifier.
old-location: pci\sriov_query_luid_vf.htm
old-project: PCI
ms.assetid: 00dddc92-08d1-4eaa-b3de-5e96c7a6d3e0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_QUERY_LUID_VF, *PSRIOV_QUERY_LUID_VF callback function pointer [Buses], PCI.sriov_query_luid_vf, SRIOV_QUERY_LUID_VF, SriovQueryLuidVf, SriovQueryLuidVf callback function [Buses], pcivirt/SriovQueryLuidVf"
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pcivirt.h
apiname:
-	*PSRIOV_QUERY_LUID_VF
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_LUID_VF callback


## -description


Gets the PCI Express SR-IOV Virtual Function (VF) given a unique identifier.


## -prototype


````
SRIOV_QUERY_LUID_VF SriovQueryLuidVf;

NTSTATUS SriovQueryLuidVf(
  _In_  PVOID  Context,
  _In_  LUID   Luid,
  _Out_ USHORT VfIndex
)
{ ... }

typedef SRIOV_QUERY_LUID_VF *PSRIOV_QUERY_LUID_VF;
````


## -parameters




### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param Luid [in]

The local unique
identifier of the VF whose index is being retrieved.


### -param VfIndex [out]

A zero-based index of the VF that is being queried.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get the identifier of a specific virtual function. 

The PF driver registers its implementation by setting the <b>QueryLuidVf</b> member of the <a href="https://msdn.microsoft.com/46c9fa94-283c-481e-9fb1-2ed63df00386">SRIOV_DEVICE_INTERFACE_STANDARD_2</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



