---
UID: NS:rilapitypes.RILADDRESS
title: RILADDRESS
author: windows-driver-content
description: This structure represents a phone number.
old-location: netvista\riladdress.htm
old-project: netvista
ms.assetid: d329069d-5455-4c37-b190-02a7bd1e789a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILADDRESS, RILADDRESS, *LPRILADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILADDRESS
req.alt-loc: rilapitypes.h
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
req.typenames: RILADDRESS, *LPRILADDRESS
req.product: Windows 10 or later.
---

# RILADDRESS structure



## -description

## -syntax

````
struct RILADDRESS {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwType;
  DWORD dwNumPlan;
  WCHAR wszAddress[MAXLENGTH_ADDRESS];
};
````


## -struct-fields

### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riladdressparammask.md">RILADDRESSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwType

The type of address. Possible values are shown in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RIL_ADDRTYPE_UNKNOWN

</td>
<td>
Unknown type

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_INTERNATIONAL

</td>
<td>
International number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_NATIONAL

</td>
<td>
National/regional number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_NETWKSPECIFIC

</td>
<td>
Network-specific number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_SUBSCRIBER

</td>
<td>
Subscriber number (protocol-specific)

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_ALPHANUM

</td>
<td>
Alphanumeric address

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_ABBREV

</td>
<td>
Abbreviated number

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_IP

</td>
<td>
IP address

</td>
</tr>
<tr>
<td>
RIL_ADDRTYPE_EMAIL

</td>
<td>
Internet email address (RFC 822)

</td>
</tr>
</table>
 


### -field dwNumPlan

The numbering scheme of the address. Possible values are shown in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RIL_NUMPLAN_UNKNOWN

</td>
<td>
Unknown numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_TELEPHONE

</td>
<td>
ISDN/telephone numbering plan (E.164/E.163)

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_DATA

</td>
<td>
Data numbering plan (X.121)

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_TELEX

</td>
<td>
Telex numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_NATIONAL

</td>
<td>
National/regional numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_PRIVATE

</td>
<td>
Private numbering plan

</td>
</tr>
<tr>
<td>
RIL_NUMPLAN_ERMES

</td>
<td>
ERMES numbering plan (ETSI DE/PS 3 01-3)

</td>
</tr>
</table>
 


### -field wszAddress

An array of address characters. The minimum length of this array is 3. When <b>dwType</b> is set to <b>RIL_ADDRTYPE_INTERNATIONAL</b>, the plus sign (+) is not prefixed to <b>wszAddress</b>. It is up to the client or modem to attach the symbol.


## -remarks
When a <b>RILADDRESS</b> represents a phone number on a UICC card, the contents of <b>wszAddress</b> are constrained to values that can be represented on the card (as defined by 3GPP TS 31.102 table 4.4). In the UICC file, a phone number is represented by a string of 4-bit nibbles padded on the right with 0xF. The defined mapping is shown in the following table.

0x0

L'0'

Digit 0

0x1

L'1'

Digit 1

0x2

L'2'

Digit 2

0x3

L'3'

Digit 3

0x4

L'4'

Digit 4

0x5

L'5'

Digit 5

0x6

L'6'

Digit 6

0x7

L'7'

Digit 7

0x8

L'8'

Digit 8

0x9

L'9'

Digit 9

0xA

L'*'

Asterisk character

0xB

L'#'

Pound character

0xC

L'p' or L'P'

DTMF control digits separator (see 3GPP TS 22.101)

0xD

L'?'

"Wild" value (see 3GPP TS 22.101)

0xE



RFU—not to be used

0xF

Padding for unused nibbles on UICC card—not to be used

In the case of the control digits separator, either uppercase or lowercase 'P' may be passed in; the output is always lowercase. The RFU value 0xE should never appear on the card, but if it does it is reported as L'e'. It is an error to pass L'e' as input.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

