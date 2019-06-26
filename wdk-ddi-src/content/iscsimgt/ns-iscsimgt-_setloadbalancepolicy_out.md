---
UID: NS:iscsimgt._SetLoadBalancePolicy_OUT
title: _SetLoadBalancePolicy_OUT (iscsimgt.h)
description: The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method.
old-location: storage\setloadbalancepolicy_out.htm
tech.root: storage
ms.assetid: 28b54f80-9268-4ccb-ac19-b1b4bfef4192
ms.date: 03/29/2018
ms.keywords: "*PSetLoadBalancePolicy_OUT, PSetLoadBalancePolicy_OUT, PSetLoadBalancePolicy_OUT structure pointer [Storage Devices], SetLoadBalancePolicy_OUT, SetLoadBalancePolicy_OUT structure [Storage Devices], _SetLoadBalancePolicy_OUT, iscsimgt/PSetLoadBalancePolicy_OUT, iscsimgt/SetLoadBalancePolicy_OUT, storage.setloadbalancepolicy_out, structs-iSCSI_32a19db4-8102-4e39-b9be-30a8a03d2732.xml"
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
- iscsimgt.h
api_name:
- SetLoadBalancePolicy_OUT
product:
- Windows
targetos: Windows
req.typenames: SetLoadBalancePolicy_OUT, *PSetLoadBalancePolicy_OUT
---

# _SetLoadBalancePolicy_OUT structure


## -description


The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method.


## -struct-fields




### -field Status

A value that provides the status of the SetLoadBalancePolicy operation.


## -remarks



You must implement this class. For a list of possible status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-lb-operations-wmi-class">MSiSCSI_LB_Operations WMI Class</a>
 

 

