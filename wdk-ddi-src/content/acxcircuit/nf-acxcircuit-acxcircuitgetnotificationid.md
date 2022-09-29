---
UID: NF:acxcircuit.AcxCircuitGetNotificationId
tech.root: audio
title: AcxCircuitGetNotificationId
ms.date: 09/29/2022
targetos: Windows
description: The AcxCircuitGetNotificationId function retrieves the Plug-n-Play notification ID for the specified ACX circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - AcxCircuitGetNotificationId
f1_keywords:
 - AcxCircuitGetNotificationId
 - acxcircuit/AcxCircuitGetNotificationId
dev_langs:
 - c++
helpviewer_keywords:
 - AcxCircuitGetNotificationId
---

## -description

The **AcxCircuitGetNotificationId** function retrieves the Plug-n-Play notification ID for the specified ACX circuit.

## -parameters

### -param Circuit

The existing ACXCIRCUIT object from which to retrieve the Plug-n-Play notification ID.

## -returns

Returns a GUID representing the Plug-n-Play notification ID for the specified *Circuit*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.1 |

<table>
  <thead>
    <th>&nbsp;</th>
    <th>&nbsp;</th>
  </thead>
  <tbody>
    <tr>
      <td><strong>Minimum ACX version</strong></td>
      <td style="text-align: left;">1.1</td>
    </tr>
  </tbody>
</table>

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
