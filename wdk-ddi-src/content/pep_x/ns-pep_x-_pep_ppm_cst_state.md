---
UID: NS:pep_x._PEP_PPM_CST_STATE
title: "_PEP_PPM_CST_STATE"
author: windows-driver-content
description: The PEP_PPM_CST_STATE structure specifies the properties of a C state (ACPI processor power state).
old-location: kernel\pep_ppm_cst_state.htm
old-project: kernel
ms.assetid: AF001441-4031-4E29-B459-1597BFCAEF4C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPEP_PPM_CST_STATE, ,, A, C, E, M, P, PEP_PPM_CST_STATE, PEP_PPM_CST_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_CST_STATE, PPEP_PPM_CST_STATE structure pointer [Kernel-Mode Driver Architecture], S, T, _, _PEP_PPM_CST_STATE, kernel.pep_ppm_cst_state, pepfx/PEP_PPM_CST_STATE, pepfx/PPEP_PPM_CST_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_CST_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_CST_STATE, *PPEP_PPM_CST_STATE, PEP_PPM_CST_STATE, *PPEP_PPM_CST_STATE
---

# _PEP_PPM_CST_STATE structure


## -description


The <b>PEP_PPM_CST_STATE</b> structure specifies the properties of a C state (ACPI processor power state).


## -syntax


````
typedef struct _PEP_PPM_CST_STATE {
  UCHAR            Type;
  USHORT           Latency;
  ULONG            Power;
  UCHAR            AddressSpaceId;
  UCHAR            BitWidth;
  UCHAR            BitOffset;
  UCHAR            AccessSize;
  PHYSICAL_ADDRESS Address;
} PEP_PPM_CST_STATE, *PPEP_PPM_CST_STATE;
````


## -struct-fields




### -field Type

The C-state type (0 = C0, 1 = C1, 2 = C2, and so on).


### -field Latency

The worst-case latency, in microseconds, to enter and exit this C state. There are no restrictions on latency size.


### -field Power

The average power consumption, in milliwatts, of the processor when in this C state.


### -field AddressSpaceId

The register address space ID (_ASI) for this C state. This member specifies the address space in which the register for this C state is located. The following IDs are defined for this member.

<table>
<tr>
<th>ID</th>
<th>Meaning</th>
</tr>
<tr>
<td>0x00</td>
<td>System memory space</td>
</tr>
<tr>
<td>0x01</td>
<td>System I/O space</td>
</tr>
<tr>
<td>0x02</td>
<td>PCI configuration space</td>
</tr>
<tr>
<td>0x03</td>
<td>Embedded controller</td>
</tr>
<tr>
<td>0x04</td>
<td>SMBus address</td>
</tr>
<tr>
<td>0x0A</td>
<td>Platform communications channel (PCC)</td>
</tr>
<tr>
<td>0x7F</td>
<td>Functional fixed hardware</td>
</tr>
</table>
 


### -field BitWidth

The register bit width (_RBW) for this C state. This member specifies the width, in bits, of the register for this C state.


### -field BitOffset

The register bit offset (_RBO) for this C state. This member specifies the offset, in bits, from the register address specified in the <b>Address</b> member to the start of the register for this C state.


### -field AccessSize

The register access size (_ASZ) code for this C state. This member specifies the number of bytes to read during an access of the register for this C state. Valid access size codes are shown in the following table.

<table>
<tr>
<th>Access size code</th>
<th>Meaning</th>
</tr>
<tr>
<td>0</td>
<td>Undefined</td>
</tr>
<tr>
<td>1</td>
<td>BYTE (1 byte)</td>
</tr>
<tr>
<td>2</td>
<td>WORD (2 bytes)</td>
</tr>
<tr>
<td>3</td>
<td>DWORD (4 bytes)</td>
</tr>
<tr>
<td>4</td>
<td>QWORD (8 bytes)</td>
</tr>
</table>
 


### -field Address

The register address (_ADR) for this C state.


## -remarks



This structure is used in conjunction with the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a> notification. The <b>IdleStates</b> member of the <a href="..\pepfx\ns-pepfx-_pep_ppm_cst_states.md">PEP_PPM_CST_STATES</a> structure is a pointer to an array of <b>PEP_PPM_CST_STATE</b> structures. The <b>Type</b> member in each element of the array should equal the array index of this member.

The values in the <b>PEP_PPM_CST_STATE</b> structure are obtained from the parameters that are specified for this C state in the _CST object in the ACPI namespace for the processor. 




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a>



<a href="..\pepfx\ns-pepfx-_pep_ppm_cst_states.md">PEP_PPM_CST_STATES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_CST_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

