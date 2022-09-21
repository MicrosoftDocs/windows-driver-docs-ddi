---
UID: NF:acxstreams.AcxRtStreamNotifyPacketComplete
tech.root: audio
title: AcxRtStreamNotifyPacketComplete
ms.date: 07/28/2022
targetos: Windows
description: The driver calls AcxRtStreamNotifyPacketComplete when a packet has completed. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - AcxRtStreamNotifyPacketComplete
f1_keywords:
 - AcxRtStreamNotifyPacketComplete
 - acxstreams/AcxRtStreamNotifyPacketComplete
dev_langs:
 - c++
---

## -description

The driver calls **AcxRtStreamNotifyPacketComplete** when a packet has completed. The packet completion time and the 0-based Packet index are included to improve client performance. The ACX framework will set any notification events associated with the stream.

## -parameters

### -param Stream

An existing ACXSTREAM Object. An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements.

### -param CompletedPacket

A 0-based Packet index indicating the packet that was just completed.

### -param QPCCompletion

The packet completion time, as returned by [KeQueryPerformanceCounter](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter). This value should be as close as possible to the actual hardware completion (for example, the driver can call KeQueryPerformanceCounter from in its Interrupt Service Routine).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

AcxRtStreamNotifyPacketComplete must be called at DISPATCH_LEVEL or below.

### Example

Example usage is shown below.

```cpp
completedPacket = (ULONG)InterlockedIncrement((LONG*)&m_CurrentPacket) - 1;

InterlockedExchange64(&m_LastPacketStart.QuadPart, m_CurrentPacketStart.QuadPart);
InterlockedExchange64(&m_CurrentPacketStart.QuadPart, QPC.QuadPart);

// Tell ACX we've completed the packet.
(void)AcxRtStreamNotifyPacketComplete(m_Stream, completedPacket, QPC.QuadPart);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
