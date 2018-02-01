---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTOUT4
title: "_DXGK_QUERYSEGMENTOUT4"
author: windows-driver-content
description: The DXGK_QUERYSEGMENTOUT4 structure contains memory segment information returned from the driver.
old-location: display\dxgk_querysegmentout4.htm
old-project: display
ms.assetid: AE6988E6-81D7-47FB-986A-B5DEE9B7215B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_QUERYSEGMENTOUT4, DXGK_QUERYSEGMENTOUT4, display.dxgk_querysegmentout4, DXGK_QUERYSEGMENTOUT4 structure [Display Devices], d3dkmddi/DXGK_QUERYSEGMENTOUT4"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
apiname:
-	DXGK_QUERYSEGMENTOUT4
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYSEGMENTOUT4
---

# _DXGK_QUERYSEGMENTOUT4 structure


## -description


The <b>DXGK_QUERYSEGMENTOUT4</b> structure contains memory segment information  returned from the driver.


## -syntax


````
typedef struct _DXGK_QUERYSEGMENTOUT4 {
  UINT   NbSegment;
  BYTE   *pSegmentDescriptor;
  UINT   PagingBufferSegmentId;
  UINT   PagingBufferSize;
  UINT   PagingBufferPrivateDataSize;
  SIZE_T SegmentDescriptorStride;
} DXGK_QUERYSEGMENTOUT4;
````


## -struct-fields




### -field NbSegment

Number of elements in the <b>pSegmentDescriptor</b> array. The <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> (<b>DXGKQAITYPE_QUERYSEGMENT4</b>) will be called twice. First time, <b>NbSegment</b> will be set to 0. The driver should return <b>STATUS_SUCCESS</b> and set <b>NbSegment</b> to the number of GPU memory segments in the adapter without accessing any other member of the structure. Second time, the driver will be called with the reported number of segments and the driver should fill all required information.


### -field pSegmentDescriptor

Pointer to the array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor4.md">DXGK_SEGMENTDESCRIPTOR4</a> structures. The size of the array element is defined by <b>SegmentDescriptorStride</b>. The <b>pSegmentDescriptor</b> type has been changed to a <b>BYTE*</b> to help enforce the use of the stride as the method of iterating the array. The driver fills the array with information about each memory segment.


### -field PagingBufferSegmentId

Segment identifier of the paging buffer. This is the index (starting from 1) of the segment in the <b>pSegmentDescriptor </b>array.


### -field PagingBufferSize

Paging buffer size.


### -field PagingBufferPrivateDataSize

Size, in bytes, of the driver-private data that will be provided with each paging buffer.


### -field SegmentDescriptorStride

Size of the elements in the <b>pSegmentDescriptor</b> array in bytes.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentin4.md">DXGK_QUERYSEGMENTIN4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYSEGMENTOUT4 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

