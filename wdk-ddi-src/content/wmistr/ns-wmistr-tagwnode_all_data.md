---
UID: NS:wmistr.tagWNODE_ALL_DATA
title: tagWNODE_ALL_DATA (wmistr.h)
description: The WNODE_ALL_DATA structure contains data for all instances of a data block or event block.
old-location: kernel\wnode_all_data.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["tagWNODE_ALL_DATA structure"]
ms.keywords: "*PWNODE_ALL_DATA, PWNODE_ALL_DATA, PWNODE_ALL_DATA structure pointer [Kernel-Mode Driver Architecture], WNODE_ALL_DATA, WNODE_ALL_DATA structure [Kernel-Mode Driver Architecture], kernel.wnode_all_data, kstruct_d_f0048b24-6d54-40c6-bb6a-8ed796a226d8.xml, tagWNODE_ALL_DATA, wmistr/PWNODE_ALL_DATA, wmistr/WNODE_ALL_DATA"
req.header: wmistr.h
req.include-header: Wmistr.h
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
req.typenames: WNODE_ALL_DATA, *PWNODE_ALL_DATA
f1_keywords:
 - tagWNODE_ALL_DATA
 - wmistr/tagWNODE_ALL_DATA
 - PWNODE_ALL_DATA
 - wmistr/PWNODE_ALL_DATA
 - WNODE_ALL_DATA
 - wmistr/WNODE_ALL_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wmistr.h
api_name:
 - WNODE_ALL_DATA
---

# tagWNODE_ALL_DATA structure


## -description

The <b>WNODE_ALL_DATA</b> structure contains data for all instances of a data block or event block.

## -struct-fields

### -field WnodeHeader

Specifies a <a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.

### -field DataBlockOffset

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> structure to the beginning of data for the first instance.

### -field InstanceCount

Indicates the number of instances whose data follows the fixed members of the <b>WNODE_ALL_DATA</b> in the buffer at <b>IrpStack->Parameters.WMI.Buffer</b>.

### -field OffsetInstanceNameOffsets

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to an array of offsets to dynamic instance names. Each instance name must be aligned on a USHORT boundary. If all instances to be returned have static instance names, WMI ignores <b>OffsetInstanceNameOffsets</b>.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.FixedInstanceSize

Indicates the size of each instance to be returned if all such instances are the same size. This member is valid only if the driver sets WNODE_FLAG_FIXED_INSTANCE_SIZE in <b>WnodeHeader.Flags</b>.

### -field DUMMYUNIONNAME.OffsetInstanceDataAndLength

If instances to be returned vary in size, <b>OffsetInstanceDataAndLength</b> is an array of <b>InstanceCount </b><b>OFFSETINSTANCEDATAANDLENGTH</b> structures that specify the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to the beginning of each instance and its length. <b>OFFSETINSTANCEDATAANDLENGTH</b> is defined as follows:


```
typedef struct {
  ULONG  OffsetInstanceData;
  ULONG  LengthInstanceData;
} OFFSETINSTANCEDATAANDLENGTH, *POFFSETINSTANCEDATAANDLENGTH;
```



Each instance must be aligned on a USHORT boundary. The <b>OffsetInstanceDataAndLength</b> member is valid only if the driver clears WNODE_FLAG_FIXED_INSTANCE_SIZE in <b>WnodeHeader.Flags</b>. 


##### - OffsetInstanceDataAndLength.LengthInstanceData

Indicates the length in bytes of the instance data.


##### - OffsetInstanceDataAndLength.OffsetInstanceData

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to the instance data.

## -remarks

A driver fills in a <b>WNODE_ALL_DATA</b> structure in response to an <a href="/windows-hardware/drivers/kernel/irp-mn-query-all-data">IRP_MN_QUERY_ALL_DATA</a> request. A driver might also generate a <b>WNODE_ALL_DATA</b> as an event.

After filling in the fixed members of the structure, a driver writes instance data and dynamic instance names (if any) at <b>DataBlockOffset</b> and <b>OffsetInstanceNameOffsets</b>, respectively, in the buffer at <b>IrpStack->Parameters.WMI.Buffer</b>. If WNODE_FLAG_FIXED_INSTANCE_SIZE is clear, the first offset follows the last element of the <b>OffsetInstanceDataAndLength</b> array, plus padding so the data begins on an 8-byte boundary.

Instance names must be USHORT aligned. Instance data must be QUADWORD aligned.

## -see-also

<a href="/windows-hardware/drivers/kernel/irp-mn-query-all-data">IRP_MN_QUERY_ALL_DATA</a>



<a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>



<a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a>
