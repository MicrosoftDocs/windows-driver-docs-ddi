---
UID: NS:ksmedia._DDVIDEOPORTCONNECT
title: _DDVIDEOPORTCONNECT (ksmedia.h)
description: The DDVIDEOPORTCONNECT structure describes a hardware video port connection.
tech.root: display
ms.date: 03/10/2023
keywords: ["DDVIDEOPORTCONNECT structure"]
ms.keywords: "*LPDDVIDEOPORTCONNECT, DDVIDEOPORTCONNECT, DDVIDEOPORTCONNECT structure [Display Devices], _DDVIDEOPORTCONNECT, ddstrcts_38f986ec-9ee1-438c-8b1f-2d07ebb06e87.xml, display.ddvideoportconnect, ksmedia/DDVIDEOPORTCONNECT"
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
targetos: Windows
req.typenames: DDVIDEOPORTCONNECT, *LPDDVIDEOPORTCONNECT
f1_keywords:
 - _DDVIDEOPORTCONNECT
 - ksmedia/_DDVIDEOPORTCONNECT
 - LPDDVIDEOPORTCONNECT
 - ksmedia/LPDDVIDEOPORTCONNECT
 - DDVIDEOPORTCONNECT
 - ksmedia/DDVIDEOPORTCONNECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - _DDVIDEOPORTCONNECT
 - LPDDVIDEOPORTCONNECT
 - DDVIDEOPORTCONNECT
---

## -description

The **DDVIDEOPORTCONNECT** structure describes a hardware video port connection.

## -struct-fields

### -field dwSize

Specifies the size in bytes of the **DDVIDEOPORTCONNECT** structure.

### -field dwPortWidth

Specifies the width of the hardware video port. This value represents the number of physical pins on the hardware video port. This member must always be filled in, even when the **guidTypeID** assumes a certain size.

### -field guidTypeID

Specifies a GUID that describes the synchronization characteristics of the hardware video port. The following port types are predefined:

| Port Type | Description |
|---|---|
| DDVPTYPE_E_HREFH_VREFH | External syncs where HREF is active high and VREF is active high. |
| DDVPTYPE_E_HREFH_VREFL | External syncs where HREF is active high and VREF is active low. |
| DDVPTYPE_E_HREFL_VREFH | External syncs where HREF is active low and VREF is active high. |
| DDVPTYPE_E_HREFL_VREFL | External syncs where HREF is active low and VREF is active low. |
| DDVPTYPE_BROOKTREE | Sync information is embedded in the data stream using the Brooktree definition. |
| DDVPTYPE_CCIR656 | Sync information is embedded in the data stream according to the CCIR656 specification. |
| DDVPTYPE_PHILIPS | Sync information is embedded in the data stream using the Philips definition. |

### -field dwFlags

Specifies a set of flags that identify the capabilities of the hardware video port connection. This member can be a bitwise OR of any of the following flags:

| Flag | Meaning |
|---|---|
| DDVPCONNECT_DISCARDSVREFDATA | The device discards any data written during the VREF period, causing this data to not be written to the frame buffer. This flag should be set only by the driver. |
| DDVPCONNECT_DOUBLECLOCK | When set by the driver, this flag indicates that the hardware video port is capable of double clocking the data. When set by the client, it indicates that the hardware video port should double clock the data. This flag is valid only in a hardware video port with a **guidTypeID** that supports an external sync. |
| DDVPCONNECT_HALFLINE | When set by the driver, this flag indicates that the hardware video port supports writing half lines into the frame buffer, sometimes causing the data to not be displayed correctly. When set by the client, it indicates that the driver may write half lines. |
| DDVPCONNECT_INTERLACED | When set by the driver, this flag indicates that the hardware video port supports interlaced signals. When set by the client, it indicates that the signal is interlaced. |
| DDVPCONNECT_INVERTPOLARITY | When set by the driver, this flag indicates that the hardware video port is capable of inverting the field polarities; that is, treating even fields as odd and vice versa. When set by the client, it indicates that the hardware video port should invert the field polarities. |
| DDVPCONNECT_SHAREEVEN | This is currently an unimplemented feature and should be ignored by the driver. |
| DDVPCONNECT_SHAREODD | This is currently an unimplemented feature and should be ignored by the driver. |
| DDVPCONNECT_VACT | When set by the driver, this flag indicates that the hardware video port is capable of using an external VACT signal. When set by the client, it indicates that the hardware video port should use the external VACT signal. |

### -field dwReserved1

Reserved for system use and should be set to zero.

## -remarks

The driver's [DdVideoPortGetConnectInfo](/windows/win32/api/ddrawint/nc-ddrawint-pdd_vportcb_getvportconnect) callback routine initializes a DDVIDEOPORTCONNECT structure for every connection that the hardware video port supports. The client can change the **dwFlags** member of one of the driver's **DDVIDEOPORTCONNECT** structures before calling the driver's [DdVideoPortCanCreate](/windows/win32/api/ddrawint/nc-ddrawint-pdd_vportcb_cancreatevideoport) callback.

## -see-also

[DdVideoPortCanCreate](/windows/win32/api/ddrawint/nc-ddrawint-pdd_vportcb_cancreatevideoport)

[DdVideoPortGetConnectInfo](/windows/win32/api/ddrawint/nc-ddrawint-pdd_vportcb_getvportconnect)
