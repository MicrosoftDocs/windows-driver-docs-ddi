---
UID: NF:video.VideoPortMapMemory
title: VideoPortMapMemory function (video.h)
description: The VideoPortMapMemory function maps a range of bus-relative physical addresses of video memory into system space or into the virtual address space of a user-mode process.
old-location: display\videoportmapmemory.htm
tech.root: display
ms.assetid: c1b54ef4-93b5-41df-8a49-8b00cbd4bcee
ms.date: 05/10/2018
ms.keywords: VideoPortMapMemory, VideoPortMapMemory function [Display Devices], VideoPort_Functions_53fef559-5fbb-4e9a-9152-b44be67bd63c.xml, display.videoportmapmemory, video/VideoPortMapMemory
ms.topic: function
f1_keywords:
 - "video/VideoPortMapMemory"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortMapMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortMapMemory function


## -description


The <b>VideoPortMapMemory</b> function maps a range of bus-relative physical addresses of video memory into system space or into the virtual address space of a user-mode process. A video miniport driver calls <b>VideoPortMapMemory</b> when it handles IOCTL_VIDEO_MAP_VIDEO_MEMORY, IOCTL_VIDEO_SHARE_VIDEO_MEMORY, or IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param PhysicalAddress

The bus-relative base address of the range to map.


### -param Length

On input, specifies the number of bytes of video memory to map. On output, receives the size of the memory actually mapped, which might be rounded to a system-determined alignment boundary. (However, the miniport and display drivers cannot access any memory that is outside the range delimited by the input value at <i>Length</i>.)


### -param InIoSpace

Pointer to a variable that indicates the location of the range. The variable can be one of the following flags or an ORed, compatible combination of these flags.

| **Flag** | **Meaning** | 
|:--|:--|
| VIDEO_MEMORY_SPACE_DENSE | Obsolete. | 
| VIDEO_MEMORY_SPACE_IO | The address range is in I/O space, not in memory space. | 
| VIDEO_MEMORY_SPACE_MEMORY | The address range is in memory space, not in I/O space. | 
| VIDEO_MEMORY_SPACE_P6CACHE | The processor aggregates a sequence of write operations, sends them to a cache line, and later flushes the cache. This flag is meaningful only if VIDEO_MEMORY_SPACE_IO is not set.
Designates the video memory as write-combined (WC). For information about WC caching, see the [Write-Combining Memory in Video Miniport Drivers](https://docs.microsoft.com/previous-versions/windows/hardware/design/dn642116(v=vs.85))  website article. | 
| VIDEO_MEMORY_SPACE_USER_MODE | The address range should be mapped into the virtual address space of a user-mode process, not into system space. This flag is meaningful only if VIDEO_MEMORY_SPACE_IO is not set. | 

### -param VirtualAddress

Pointer to a variable that, on input, is either <b>NULL</b> or a handle to a user-mode process. If the input value is <b>NULL</b>, this routine maps the video memory into system space. Otherwise, this routine maps the video memory into the virtual address space of the user-mode process that is identified by the handle. On output, receives the base virtual address of the mapping.


## -returns



<b>VideoPortMapMemory</b> returns NO_ERROR if it successfully mapped the specified range; otherwise, it returns ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortMapMemory</b> runs in kernel mode within the same context as the user-mode thread that initiated the call.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a> and <b>VideoPortMapMemory</b> can both be called by the video miniport driver to map video memory into a virtual address space. If you call both of these functions to map the same physical addresses, or if you call one of the functions more than once to map the same physical addresses, you might have more than one virtual-address range that maps to the same physical-address range. In that case, you must set the VIDEO_MEMORY_SPACE_P6CACHE flag of the <i>InIoSpace</i> parameter to the same value in all of those calls.

Every universal memory architecture (UMA) display device uses a frame buffer that is located in main memory rather than on a PCI bus. In this case, do not call <b>VideoPortMapMemory</b> to map the frame buffer. To map a UMA frame buffer into system space, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmapiospace">MmMapIoSpace</a>. To map a UMA frame buffer into the virtual address space of a user-mode process, perform the following steps:

<ol>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwopensection">ZwOpenSection</a> to get a handle to the operating system's physical-memory section object, which is named <b>\Device\PhysicalMemory</b>.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwmapviewofsection">ZwMapViewOfSection</a> to map a view of the frame buffer into the virtual address space of the current process.

</li>
</ol>
The following example shows how to map a UMA frame buffer into the virtual address space of the current process.

```cpp
UNICODE_STRING    UnicodeString;          // Name of the section object
OBJECT_ATTRIBUTES ObjectAttributes;       // Description for the section object
HANDLE            hPhysicalMemoryHandle;  // Handle to the section object
PHYSICAL_ADDRESS  MappedLength;           // Length of the frame buffer

PHYSICAL_ADDRESS  MappedBase;             // Base physical address (CPU-relative)
                                          // of the frame buffer

// Allocate a variable to receive the base virtual address of the view.
// Set it to NULL for input to ZwMapViewOfSection, to specify that the memory
// manager (rather than the caller) should determine the base virtual address.
PVOID pViewBase = NULL;

RtlInitUnicodeString(&UnicodeString, L"\\Device\\PhysicalMemory");

InitializeObjectAttributes(
   &ObjectAttributes,
   &UnicodeString,
   OBJ_CASE_INSENSITIVE | OBJ_KERNEL_HANDLE,
   (HANDLE) NULL,
   (PSECURITY_DESCRIPTOR) NULL);

// Open a handle to the physical-memory section object.
ntStatus = ZwOpenSection(&hPhysicalMemoryHandle, SECTION_ALL_ACCESS, &ObjectAttributes);

if(NT_SUCCESS(ntStatus))
{
   ntStatus = ZwMapViewOfSection(
      hPhysicalMemoryHandle,
      NtCurrentProcess(),
      &pViewBase,
      0L,
      (ULONG_PTR)MappedLength.QuadPart,
      &MappedBase,
      (PULONG_PTR)(&(MappedLength.QuadPart)),
      ViewUnmap,
      0,
      PAGE_READWRITE | PAGE_WRITECOMBINE);

   if(NT_SUCCESS(ntStatus))
   {
      // pViewBase holds the base virtual address of the view.
   }

   // Close the handle to the physical-memory section object.
   ZwClose(hPhysicalMemoryHandle);
}
```

Miniport drivers should use <b>VideoPortMapMemory</b> to manage video adapters that allow the video <a href="https://docs.microsoft.com/windows-hardware/drivers/">frame buffer</a> to be completely mapped at all times. That is, miniport drivers for adapters that are not restricted to using <a href="https://docs.microsoft.com/windows-hardware/drivers/">banks</a> to map a slice at a time can use the more efficient <b>VideoPortMapMemory</b>. 

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddvdeo/ni-ntddvdeo-ioctl_video_map_video_memory">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>
 

 

