---
UID: NF:d3dkmthk.D3DKMTRegisterVailProcess
tech.root: display
title: D3DKMTRegisterVailProcess
ms.date: 04/13/2022
targetos: Windows
description: Learn more about the D3DKMTRegisterVailProcess function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: gdi32.dll
req.header: d3dkmthk.h (include d3dkmthk.h)
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: gdi32.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTRegisterVailProcess
f1_keywords:
 - D3DKMTRegisterVailProcess
 - d3dkmthk/D3DKMTRegisterVailProcess
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTRegisterVailProcess
---

## -description

The **D3DKMTRegisterVailProcess** function registers the current process as one that can share GPU allocations between a guest virtual machine (VM) and the host.

## -parameters

### -param unnamedParam1

[in] **VirtualMachineGuid**, which is a pointer to the GUID associated with a running VM. The VM must have at least one virtual GPU assigned.

## -returns

**D3DKMTRegisterVailProcess** returns an NTSTATUS code such as one of the following values:

| Return code                        | Description |
| -----------                        | ----------- |
| STATUS_SUCCESS                     | Process registration was successful. |
| STATUS_ACCESS_DENIED               | The process does not have enough privileges to call this API. Note that other status codes could be returned in this case. |
| STATUS_INVALID_PARAMETER           | The value passed in **VirtualMachineGuid** is not valid. |
| STATUS_GRAPHICS_VAIL_STATE_CHANGED | The VM does not have a virtual GPU assigned. |
| STATUS_INVALID_DISPOSITION         | The process does not have graphics context created. |
| STATUS_NOT_FOUND                   | A VM with the given GUID was not found. |

Other status codes could be returned as well.

## -remarks

The calling process must have the same privileges as the Remote Desktop (RDP) client process that was created for the VM instance specified by the **VirtualMachineGuid** parameter.
