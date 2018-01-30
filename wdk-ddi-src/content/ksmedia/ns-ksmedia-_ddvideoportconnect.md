---
UID: NS:ksmedia._DDVIDEOPORTCONNECT
title: "_DDVIDEOPORTCONNECT"
author: windows-driver-content
description: The DDVIDEOPORTCONNECT structure describes a hardware video port connection.
old-location: display\ddvideoportconnect.htm
old-project: display
ms.assetid: 54c1bb05-37a8-4841-808b-2eb9d1ecd7a3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DDVIDEOPORTCONNECT, *LPDDVIDEOPORTCONNECT, display.ddvideoportconnect, DDVIDEOPORTCONNECT structure [Display Devices], ddstrcts_38f986ec-9ee1-438c-8b1f-2d07ebb06e87.xml, ksmedia/DDVIDEOPORTCONNECT, _DDVIDEOPORTCONNECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	DDVIDEOPORTCONNECT
product: Windows
targetos: Windows
req.typenames: "*LPDDVIDEOPORTCONNECT, DDVIDEOPORTCONNECT"
---

# _DDVIDEOPORTCONNECT structure


## -description


The DDVIDEOPORTCONNECT structure describes a hardware video port connection.


## -syntax


````
typedef struct _DDVIDEOPORTCONNECT {
  DWORD     dwSize;
  DWORD     dwPortWidth;
  GUID      guidTypeID;
  DWORD     dwFlags;
  ULONG_PTR dwReserved1;
} DDVIDEOPORTCONNECT;
````


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


The driver's <a href="https://msdn.microsoft.com/b6be5f94-6d4d-4f7a-a8d9-15bfc7a15d3b">DdVideoPortGetConnectInfo</a> callback routine initializes a DDVIDEOPORTCONNECT structure for every connection that the hardware video port supports. The client can change the <b>dwFlags</b> member of one of the driver's DDVIDEOPORTCONNECT structures before calling the driver's <a href="https://msdn.microsoft.com/742c7af2-0611-4cca-b18c-e14b18068d7e">DdVideoPortCanCreate</a> callback.



## -see-also

<a href="https://msdn.microsoft.com/b6be5f94-6d4d-4f7a-a8d9-15bfc7a15d3b">DdVideoPortGetConnectInfo</a>

<a href="https://msdn.microsoft.com/742c7af2-0611-4cca-b18c-e14b18068d7e">DdVideoPortCanCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDVIDEOPORTCONNECT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

