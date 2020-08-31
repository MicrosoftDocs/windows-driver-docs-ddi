---
UID: NS:winddiui._DOCEVENT_FILTER
title: _DOCEVENT_FILTER (winddiui.h)
description: The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See DrvDocumentEvent for a complete list of the document events.
old-location: print\docevent_filter.htm
tech.root: print
ms.assetid: f486efdb-79fd-4c57-bff6-75a0dbd68cc0
ms.date: 04/20/2018
keywords: ["DOCEVENT_FILTER structure"]
ms.keywords: "*PDOCEVENT_FILTER, DOCEVENT_FILTER, DOCEVENT_FILTER structure [Print Devices], PDOCEVENT_FILTER, PDOCEVENT_FILTER structure pointer [Print Devices], _DOCEVENT_FILTER, print.docevent_filter, print_interface-graphics_ddc1c545-869f-440d-a364-7cd90ca189e0.xml, winddiui/DOCEVENT_FILTER, winddiui/PDOCEVENT_FILTER"
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.typenames: DOCEVENT_FILTER, *PDOCEVENT_FILTER
f1_keywords:
 - _DOCEVENT_FILTER
 - winddiui/_DOCEVENT_FILTER
 - PDOCEVENT_FILTER
 - winddiui/PDOCEVENT_FILTER
 - DOCEVENT_FILTER
 - winddiui/DOCEVENT_FILTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DOCEVENT_FILTER
---

# _DOCEVENT_FILTER structure


## -description

The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) for a complete list of the document events.

## -struct-fields

### -field cbSize

Spooler-supplied size, in bytes, of this structure. The spooler initializes this member to **sizeof**(DOCEVENT_FILTER).

### -field cElementsAllocated

Spooler-supplied number of elements in the **aDocEventCall** array member. The spooler initializes this member to DOCUMENTEVENT_LAST - 1. (The DOCUMENTEVENT_LAST constant is defined in header file Winddiui.h.)

### -field cElementsNeeded

Driver-supplied total number of elements needed in the **aDocEventCall** array member. The spooler initializes this member to 0XFFFFFFFF. For more information, see the following Remarks section.

### -field cElementsReturned

Driver-supplied number of DOCUMENTEVENT_**XXX **events that it placed in the **aDocEventCall** array member. The spooler initializes this member to 0XFFFFFFFF. For more information, see the following Remarks section.

### -field aDocEventCall

Driver-filled array of DWORDs listing all of the DOCUMENTEVENT_**XXX** events to which the printer driver will respond. The spooler initializes this member to 0.

## -remarks

The printer driver lists the events to which it will respond in the DOCEVENT_FILTER structure. Because this limits the number of calls to the driver the spooler needs to make, printer performance is enhanced. When the spooler makes a call to the [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) DDI with its **iEsc** parameter set to DOCUMENTEVENT_QUERYFILTER, the spooler allocates a buffer that contains a DOCEVENT_FILTER structure, including its **aDocEventCall** array. The amount of memory allocated for the buffer is:

```cpp
sizeof(DOCEVENT_FILTER) + sizeof(DWORD) * (DOCUMENTEVENT_LAST - 2)
```

After allocating a buffer that contains a DOCEVENT_FILTER structure, the spooler initializes the structure members to the following values:

| Member | Initialized to: |
| --- | --- |
| **cbSize** | 0 |
| **cElementsAllocated** | DOCUMENTEVENT_LAST - 1<br>The DOCUMENTEVENT_LAST constant is defined in winddiui.h. |
| **cElementsNeeded** | 0XFFFFFFFF |
| **cElementsReturned** | 0XFFFFFFFF |
| **aDocEventCall** | 0 |

After the spooler has initialized the structure members to the values shown in the preceding table, it then calls [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent). When this function returns, the spooler inspects the **cElementsNeeded** and **cElementsReturned** members to see if either has been changed. If the driver has written to one of these members, but not the other, the spooler interprets the unwritten-to member as having the value 0.

If the driver supports DOCUMENTEVENT_QUERYFILTER:

- If the **aDocEventCall** array is large enough to contain all of the DOCUMENTEVENT_**XXX** events the printer driver intends to place in it, the printer driver:
  - Fills the array with those events
  - Sets the **cElementsReturned** member to that number of events (which should be less than or equal to **cElementsAllocated**)
  - Leaves **cElementsNeeded** unchanged
  - Returns DOCUMENTEVENT_SUCCESS

In this case, the spooler uses the first **cElementsReturned** values in the **aDocEventCall** array.

> [!NOTE]
> The DOCUMENTEVENT_CREATEDCPRE event is treated in a special way. When the spooler calls [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) with the **iEsc** parameter set to DOCUMENTEVENT_CREATEDCPRE, the spooler uses the return value to determine whether future calls to this function are necessary. Unlike other DOCUMENTEVENT_**XXX** events, the printer driver always receives calls to **DrvDocumentEvent** with DOCUMENTEVENT_CREATEDCPRE, whether this event is filtered out or not.

- If the **aDocEventCall** array is not large enough to contain all of the DOCUMENTEVENT_**XXX** events the printer driver intends to place in it, the printer driver should:
  - Set **cElementsNeeded** to the number of events to which it intends to respond (which should be greater than **cElementsAllocated**)
  - Leave **cElementsReturned** unchanged
  - Return DOCUMENTEVENT_SUCCESS

In this case, the spooler then allocates a new buffer that is sufficiently large, and then makes another call to [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) with DOCUMENTEVENT_QUERYFILTER.

If the driver does not support the DOCUMENTEVENT_QUERYFILTER event, it should return DOCUMENTEVENT_UNSUPPORTED. If the driver does support DOCUMENTEVENT_QUERYFILTER, but encounters internal errors when it handles this event, it should return DOCUMENTEVENT_FAILURE. In either case, the spooler is not able to retrieve the event filter from the driver, so it continues in its behavior of calling [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) for all events.

## -see-also

[DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent)

