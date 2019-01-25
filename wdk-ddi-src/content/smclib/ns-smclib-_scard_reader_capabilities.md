---
UID: NS:smclib._SCARD_READER_CAPABILITIES
title: "_SCARD_READER_CAPABILITIES" (smclib.h)
description: The SCARD_READER_CAPABILITIES structure holds state information about the smart card reader.
old-location: smartcrd\scard_reader_capabilities.htm
tech.root: smartcrd
ms.assetid: f55b74d0-d545-419a-87fb-c320f789aaf4
ms.date: 02/22/2018
ms.keywords: "*PSCARD_READER_CAPABILITIES, *PSCARD_READER_CAPABILITIES structure [Smart Card Reader Devices], SCARD_READER_CAPABILITIES, SCARD_READER_CAPABILITIES structure [Smart Card Reader Devices], _SCARD_READER_CAPABILITIES, scstruct_bf7b8868-e647-42c5-8e1d-18681db95b08.xml, smartcrd.scard_reader_capabilities, smclib/*PSCARD_READER_CAPABILITIES, smclib/SCARD_READER_CAPABILITIES"
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Smclib.h
api_name:
-	SCARD_READER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: SCARD_READER_CAPABILITIES, *PSCARD_READER_CAPABILITIES
---

# _SCARD_READER_CAPABILITIES structure


## -description


The SCARD_READER_CAPABILITIES structure holds state information about the smart card reader. 


## -struct-fields




### -field SupportedProtocols

Must be set to a bitmask that reflects the asynchronous or synchronous protocols that the card reader and card reader driver support. This member is required.   


### -field Reserved

Reserved for system use. 


### -field ReaderType

This member contains the reader type and is required. This member can have one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SCARD_READER_TYPE_SERIAL

</td>
<td>
Serial reader

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_PCMCIA

</td>
<td>
PCMCIA reader

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_KEYBOARD

</td>
<td>
Keyboard-attached reader

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_USB

</td>
<td>
USB reader

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_PARALELL

</td>
<td>
Parallel reader 

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_SCSI

</td>
<td>
SCSI reader 

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_IDE

</td>
<td>
IDE reader 

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_TPM

</td>
<td>
Reader that uses a TPM chip for key material storage and cryptographic operations

</td>
</tr>
<tr>
<td>
SCARD_READER_TYPE_VENDOR

</td>
<td>
Reader that uses a proprietary vendor bus 

</td>
</tr>
</table>
 


### -field MechProperties

Contains a value that is formed by taking a bitwise OR of all applicable reader properties shown in the following table. This member is optional. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SCARD_READER_SWALLOWS

</td>
<td>
Reader has a swallowing mechanism.

</td>
</tr>
<tr>
<td>
SCARD_READER_EJECTS

</td>
<td>
Reader can eject the smart card.

</td>
</tr>
<tr>
<td>
SCARD_READER_CONFISCATES

</td>
<td>
Reader can swallow the smart card.

</td>
</tr>
</table>
 


### -field CurrentState

This member contains the status of the card and is required. This member can have one of the values listed in the following table.

<table>
<tr>
<th>Status</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SCARD_UNKNOWN

</td>
<td>
The reader does not have information about the status.

</td>
</tr>
<tr>
<td>
SCARD_ABSENT

</td>
<td>
No smart card is inserted.

</td>
</tr>
<tr>
<td>
SCARD_PRESENT

</td>
<td>
A smart card is inserted.

</td>
</tr>
<tr>
<td>
SCARD_SWALLOWED

</td>
<td>
A smart card is inserted and the reader has swallowed it.

</td>
</tr>
<tr>
<td>
SCARD_POWERED

</td>
<td>
The smart card is turned on, but the reader does not recognize its mode.

</td>
</tr>
<tr>
<td>
SCARD_NEGOTIABLE

</td>
<td>
A smart card is inserted and awaits protocol negotiation.

</td>
</tr>
<tr>
<td>
SCARD_SPECIFIC

</td>
<td>
A smart card is inserted and a protocol has been selected.

</td>
</tr>
</table>
 

Access to this field must be sequentialized by using the spin lock pointed to by the <b>OsData-&gt;SpinLock</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548974">SMARTCARD_EXTENSION</a>. 


### -field Channel

Contains the logical channel number. This member is optional. The exact meaning of this member depends on the type of smart card, as shown in the following table. 

<table>
<tr>
<th>Type of smart card</th>
<th>Meaning of value in channel field</th>
</tr>
<tr>
<td>
Serial reader

</td>
<td>
Port number

</td>
</tr>
<tr>
<td>
Parallel reader

</td>
<td>
Port number

</td>
</tr>
<tr>
<td>
SCSI reader

</td>
<td>
SCSI ID

</td>
</tr>
<tr>
<td>
Keyboard reader

</td>
<td>
0

</td>
</tr>
<tr>
<td>
USB reader

</td>
<td>
Device number

</td>
</tr>
</table>
 

For more information, see Part 3 of the <i>Interoperability Specification for ICCs and Personal Computer Systems</i>. 


### -field CLKFrequency


      A structure with the following members:


### -field CLKFrequency.Default

Contains the standard clock frequency at which the reader runs, in kilohertz, and encoded in little-endian format. For example, 3.58 MHz is encoded as 3580. This member is required. 


### -field CLKFrequency.Max

Contains the maximum clock frequency at which the reader can run, in kilohertz, and encoded in little-endian format. This member is required. 


### -field DataRate


      A structure with the following members:
     


### -field DataRate.Default

Contains the standard data rate of the reader, in units of bits per second, and encoded in little-endian format. This member is required. 


### -field DataRate.Max

Contains the maximum data rate of the reader, in units of bits per second, and encoded in little-endian format. This member is required.  


### -field MaxIFSD

Contains the maximum buffer size of the reader. This value informs the smart card at the beginning of a T=1 transmission of the maximum number of bytes that can be received in one packet. This member is required.  


### -field PowerMgmtSupport

Indicates the type of power management that the card supports. A value of zero indicates that the smart card does not support power management. 


### -field CardConfiscated

If <b>TRUE</b>, indicates that the smart card was confiscated.


### -field DataRatesSupported


      A structure with the following members:
     


### -field DataRatesSupported.List

Contains a list of data rates, in bits per second, that are supported by the reader. This member is used with the PTS request. The reader driver usually sets this member to a pointer to a static array of unsigned long values that contain the supported data rates. If the reader does not support different data rates, leave this member empty. This member is optional.


### -field DataRatesSupported.Entries

Contains the number of linked list entries in DataRatesSupported.List. This member is optional. 


### -field _DataRatesSupported


      A structure with the following members:
     


### -field CLKFrequenciesSupported


      A structure with the following members:
      
     


### -field CLKFrequenciesSupported.List

Contains a list of clock frequencies, in kilohertz, that are supported by the reader. This member is used with the PTS request. The driver usually sets this member to a pointer to a static array of unsigned long values that contain the supported clock frequencies. If the reader does not support different clock frequencies, leave this member empty. This member is optional. 


### -field CLKFrequenciesSupported.Entries

Contains the number of linked list entries of CLKFrquenciesSupported.List. This member is optional. 


### -field _CLKFrequenciesSupported


      A structure with the following members:
      
     


### -field Reserved1

Reserved for system use.


## -remarks



This structure must be maintained by the smart card reader driver. 



