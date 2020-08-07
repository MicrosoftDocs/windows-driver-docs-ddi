---
UID: NS:ksmedia._DDVIDEOPORTCONNECT
title: _DDVIDEOPORTCONNECT (ksmedia.h)
description: The DDVIDEOPORTCONNECT structure describes a hardware video port connection.
old-location: display\ddvideoportconnect.htm
tech.root: display
ms.assetid: 54c1bb05-37a8-4841-808b-2eb9d1ecd7a3
ms.date: 05/10/2018
keywords: ["DDVIDEOPORTCONNECT structure"]
ms.keywords: "*LPDDVIDEOPORTCONNECT, DDVIDEOPORTCONNECT, DDVIDEOPORTCONNECT structure [Display Devices], _DDVIDEOPORTCONNECT, ddstrcts_38f986ec-9ee1-438c-8b1f-2d07ebb06e87.xml, display.ddvideoportconnect, ksmedia/DDVIDEOPORTCONNECT"
f1_keywords:
 - "ksmedia/DDVIDEOPORTCONNECT"
 - "DDVIDEOPORTCONNECT"
req.header: ksmedia.h
req.include-header: Dvp.h
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
- ksmedia.h
api_name:
- DDVIDEOPORTCONNECT
targetos: Windows
req.typenames: DDVIDEOPORTCONNECT, *LPDDVIDEOPORTCONNECT
---

# _DDVIDEOPORTCONNECT structure


## -description


The DDVIDEOPORTCONNECT structure describes a hardware video port connection.


## -struct-fields




### -field dwSize

Specifies the size in bytes of the DDVIDEOPORTCONNECT structure.


### -field dwPortWidth

Specifies the width of the hardware video port. This value represents the number of physical pins on the hardware video port. This member must always be filled in, even when the <b>guidTypeID</b> assumes a certain size. 


### -field guidTypeID

Specifies a GUID that describes the synchronization characteristics of the hardware video port. The following port types are predefined:

<table>
<tr>
<th>Port Type</th>
<th>Description</th>
</tr>
<tr>
<td>
DDVPTYPE_E_HREFH_VREFH

</td>
<td>
External syncs where HREF is active high and VREF is active high.

</td>
</tr>
<tr>
<td>
DDVPTYPE_E_HREFH_VREFL

</td>
<td>
External syncs where HREF is active high and VREF is active low.

</td>
</tr>
<tr>
<td>
DDVPTYPE_E_HREFL_VREFH

</td>
<td>
External syncs where HREF is active low and VREF is active high.

</td>
</tr>
<tr>
<td>
DDVPTYPE_E_HREFL_VREFL

</td>
<td>
External syncs where HREF is active low and VREF is active low.

</td>
</tr>
<tr>
<td>
DDVPTYPE_BROOKTREE

</td>
<td>
Sync information is embedded in the data stream using the Brooktree definition.

</td>
</tr>
<tr>
<td>
DDVPTYPE_CCIR656

</td>
<td>
Sync information is embedded in the data stream according to the CCIR656 specification.

</td>
</tr>
<tr>
<td>
DDVPTYPE_PHILIPS

</td>
<td>
Sync information is embedded in the data stream using the Philips definition.

</td>
</tr>
</table>
 


### -field dwFlags

Specifies a set of flags that identify the capabilities of the hardware video port connection. This member can be a bitwise OR of any of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDVPCONNECT_DISCARDSVREFDATA

</td>
<td>
The device discards any data written during the VREF period, causing this data to not be written to the frame buffer. This flag should be set only by the driver.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_DOUBLECLOCK

</td>
<td>
When set by the driver, this flag indicates that the hardware video port is capable of double clocking the data. When set by the client, it indicates that the hardware video port should double clock the data. This flag is valid only in a hardware video port with a <b>guidTypeID</b> that supports an external sync.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_HALFLINE

</td>
<td>
When set by the driver, this flag indicates that the hardware video port supports writing half lines into the frame buffer, sometimes causing the data to not be displayed correctly. When set by the client, it indicates that the driver may write half lines.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_INTERLACED

</td>
<td>
When set by the driver, this flag indicates that the hardware video port supports interlaced signals. When set by the client, it indicates that the signal is interlaced.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_INVERTPOLARITY

</td>
<td>
When set by the driver, this flag indicates that the hardware video port is capable of inverting the field polarities; that is, treating even fields as odd and vice versa. When set by the client, it indicates that the hardware video port should invert the field polarities.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_SHAREEVEN

</td>
<td>
This is currently an unimplemented feature and should be ignored by the driver.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_SHAREODD

</td>
<td>
This is currently an unimplemented feature and should be ignored by the driver.

</td>
</tr>
<tr>
<td>
DDVPCONNECT_VACT

</td>
<td>
When set by the driver, this flag indicates that the hardware video port is capable of using an external VACT signal. When set by the client, it indicates that the hardware video port should use the external VACT signal.

</td>
</tr>
</table>
 


### -field dwReserved1

Reserved for system use and should be set to zero. 


## -remarks



The driver's <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_vportcb_getvportconnect">DdVideoPortGetConnectInfo</a> callback routine initializes a DDVIDEOPORTCONNECT structure for every connection that the hardware video port supports. The client can change the <b>dwFlags</b> member of one of the driver's DDVIDEOPORTCONNECT structures before calling the driver's <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_vportcb_cancreatevideoport">DdVideoPortCanCreate</a> callback.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_vportcb_cancreatevideoport">DdVideoPortCanCreate</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_vportcb_getvportconnect">DdVideoPortGetConnectInfo</a>
 

 

