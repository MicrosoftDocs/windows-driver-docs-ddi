---
UID: NS:wmistr.tagWNODE_ALL_DATA
title: tagWNODE_ALL_DATA
author: windows-driver-content
description: The WNODE_ALL_DATA structure contains data for all instances of a data block or event block.
old-location: kernel\wnode_all_data.htm
old-project: kernel
ms.assetid: 15582270-6cc4-43d4-b9e6-dceab3bc092d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PWNODE_ALL_DATA, PWNODE_ALL_DATA, PWNODE_ALL_DATA structure pointer [Kernel-Mode Driver Architecture], WNODE_ALL_DATA, WNODE_ALL_DATA structure [Kernel-Mode Driver Architecture], kernel.wnode_all_data, kstruct_d_f0048b24-6d54-40c6-bb6a-8ed796a226d8.xml, tagWNODE_ALL_DATA, wmistr/PWNODE_ALL_DATA, wmistr/WNODE_ALL_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wmistr.h
api_name:
-	WNODE_ALL_DATA
product: Windows
targetos: Windows
req.typenames: WNODE_ALL_DATA, *PWNODE_ALL_DATA
req.product: Windows 10 or later.
---

# tagWNODE_ALL_DATA structure


## -description


The <b>WNODE_ALL_DATA</b> structure contains data for all instances of a data block or event block.


## -syntax


````
typedef struct tagWNODE_ALL_DATA {
  struct _WNODE_HEADER  WnodeHeader;
  ULONG                DataBlockOffset;
  ULONG                InstanceCount;
  ULONG                OffsetInstanceNameOffsets;
  union {
    ULONG                       FixedInstanceSize;
    OFFSETINSTANCEDATAANDLENGTH OffsetInstanceDataAndLength[];
  };
} WNODE_ALL_DATA, *PWNODE_ALL_DATA;
````


## -struct-fields




### -field WnodeHeader

Specifies a <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field DataBlockOffset

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> structure to the beginning of data for the first instance. 


### -field InstanceCount

Indicates the number of instances whose data follows the fixed members of the <b>WNODE_ALL_DATA</b> in the buffer at <b>IrpStack-&gt;Parameters.WMI.Buffer</b>. 


### -field OffsetInstanceNameOffsets

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to an array of offsets to dynamic instance names. Each instance name must be aligned on a USHORT boundary. If all instances to be returned have static instance names, WMI ignores <b>OffsetInstanceNameOffsets</b>.


### -field DUMMYUNIONNAME

 




#### - FixedInstanceSize

Indicates the size of each instance to be returned if all such instances are the same size. This member is valid only if the driver sets WNODE_FLAG_FIXED_INSTANCE_SIZE in <b>WnodeHeader.Flags</b>. 


#### - OffsetInstanceDataAndLength

If instances to be returned vary in size, <b>OffsetInstanceDataAndLength</b> is an array of <b>InstanceCount </b><b>OFFSETINSTANCEDATAANDLENGTH</b> structures that specify the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to the beginning of each instance and its length. <b>OFFSETINSTANCEDATAANDLENGTH</b> is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct {
  ULONG  OffsetInstanceData;
  ULONG  LengthInstanceData;
} OFFSETINSTANCEDATAANDLENGTH, *POFFSETINSTANCEDATAANDLENGTH;</pre>
</td>
</tr>
</table></span></div>




#### OffsetInstanceData

Indicates the offset in bytes from the beginning of the <b>WNODE_ALL_DATA</b> to the instance data.



#### LengthInstanceData

Indicates the length in bytes of the instance data.

Each instance must be aligned on a USHORT boundary. The <b>OffsetInstanceDataAndLength</b> member is valid only if the driver clears WNODE_FLAG_FIXED_INSTANCE_SIZE in <b>WnodeHeader.Flags</b>. 


## -remarks



A driver fills in a <b>WNODE_ALL_DATA</b> structure in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a> request. A driver might also generate a <b>WNODE_ALL_DATA</b> as an event.

After filling in the fixed members of the structure, a driver writes instance data and dynamic instance names (if any) at <b>DataBlockOffset</b> and <b>OffsetInstanceNameOffsets</b>, respectively, in the buffer at <b>IrpStack-&gt;Parameters.WMI.Buffer</b>. If WNODE_FLAG_FIXED_INSTANCE_SIZE is clear, the first offset follows the last element of the <b>OffsetInstanceDataAndLength</b> array, plus padding so the data begins on an 8-byte boundary.

Instance names must be USHORT aligned. Instance data must be QUADWORD aligned.




## -see-also

<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a>



<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WNODE_ALL_DATA structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

