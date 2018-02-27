---
UID: NA:avcstrm
ms.assetid: 95ad8480-00a5-327d-bbf8-cb0d47180196
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Avcstrm.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Avcstrm.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_AVCSTRM_BUFFER_STRUCT structure](ns-avcstrm-_avcstrm_buffer_struct.md) | The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to avcstrm.sys for read or write operations. |
| [_AVCSTRM_FORMAT_INFO structure](ns-avcstrm-_avcstrm_format_info.md) | The AVCSTRM_FORMAT_INFO structure is used to describe a data stream. |
| [_AVCSTRM_OPEN_STRUCT structure](ns-avcstrm-_avcstrm_open_struct.md) | The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened. |
| [_AVC_STREAM_REQUEST_BLOCK structure](ns-avcstrm-_avc_stream_request_block.md) | The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by avcstrm.sys. |
| [_CIP_HDR1 structure](ns-avcstrm-_cip_hdr1.md) | The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair). |
| [_CIP_HDR2_FDF structure](ns-avcstrm-_cip_hdr2_fdf.md) | The CIP_HDR2_FDF structure describes the second quadlet of a CIP header pair. |
| [_CIP_HDR2_MPEGTS structure](ns-avcstrm-_cip_hdr2_mpegts.md) | The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream. |
| [_CIP_HDR2_SYT structure](ns-avcstrm-_cip_hdr2_syt.md) | The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream. |
| [_DVINFO structure](ns-avcstrm-_dvinfo.md) | The DVINFO structure describes a DV stream format including its default streaming source information and stream control information. |
| [tagKS_DATAFORMAT_DV_AVC structure](ns-avcstrm-tagks_dataformat_dv_avc.md) | The KS_DATAFORMAT_DV_AVC structure stores the data format for an AV/C digital video connection. |
| [tagKS_DATAFORMAT_MPEG2TS_AVC structure](ns-avcstrm-tagks_dataformat_mpeg2ts_avc.md) | The KS_DATAFORMAT_MPEG2TS_AVC structure stores the data format for an AV/C MPEG2 connection. |
| [tagKS_DATARANGE_DVVIDEO structure](ns-avcstrm-tagks_datarange_dvvideo.md) | The KS_DATARANGE_DV_AVC structure stores a range of digital video formats. |
| [tagKS_DATARANGE_DV_AVC structure](ns-avcstrm-tagks_datarange_dv_avc.md) | The KS_DATARANGE_DV_AVC structure stores a range of AV/C digital video formats. |
| [tagKS_DATARANGE_MPEG2TS_AVC structure](ns-avcstrm-tagks_datarange_mpeg2ts_avc.md) | The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_AVCSTRM_CLASS IOCTL](ni-avcstrm-ioctl_avcstrm_class.md) | An AV/C subunit driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP, with the IoControlCode member set to IOCTL_AVCSTRM_CLASS, to communicate with avcstrm.sys. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_AVCSTRM_FORMAT enumeration](ne-avcstrm-_avcstrm_format.md) | The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by avcstrm.sys. |
| [_AVCSTRM_FUNCTION enumeration](ne-avcstrm-_avcstrm_function.md) | The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the avcstrm.sys driver. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [INIT_AVCSTRM_HEADER macro](nf-avcstrm-init_avcstrm_header.md) | The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure. |
