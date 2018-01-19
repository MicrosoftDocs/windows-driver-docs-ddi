---
UID: NI:mountmgr.IOCTL_MOUNTMGR_CREATE_POINT
title: IOCTL_MOUNTMGR_CREATE_POINT
author: windows-driver-content
description: The mount manager clients can use this IOCTL to request that the mount manager create a persistent symbolic link name for the indicated volume.
old-location: storage\ioctl_mountmgr_create_point.htm
old-project: storage
ms.assetid: 580af31d-4122-48fe-a9da-097787f87620
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountmgr.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_MOUNTMGR_CREATE_POINT
req.alt-loc: Mountmgr.h
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
req.typenames: *PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_CREATE_POINT IOCTL



## -description
The mount manager clients can use this IOCTL to request that the mount manager create a persistent symbolic link name for the indicated volume. For a discussion of the various sorts of persistent symbolic links managed by the mount manager, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>.

The input to this request is the persistent symbolic link name to be created and a name that is already valid for purposes of identifying the volume. The name given for purposes of identifying the volume can be of any type: a unique volume name, a symbolic link name, or a nonpersistent device name. If the new persistent name is not already in use, the call will succeed and the mount manager database will be modified to reflect that the new persistent name belongs to the volume. If the mount manager database already contains the new persistent name but the volume that owns that name is not in the system, this call will overwrite ownership of the given persistent name.

The mount manager allows the creation of a new persistent symbolic link name even if it has not yet been notified of the given volume in the MOUNTDEV_MOUNTED_DEVICE_GUID device interface notification. In such a case, the mount manager simply creates the symbolic link and updates the mount manager database. 

The mount manager enforces a policy of at most one persistent drive letter per volume. If an <b>IOCTL_MOUNTMGR_CREATE_POINT</b> request is sent with a drive letter, the request will fail if there is already a drive letter assigned to the volume, unless the mount manager has not yet been notified of the volume by means of the MOUNTDEV_MOUNTED_DEVICE_GUID device interface notification. In the latter case, the call succeeds and the mount manager purges the mount manager database of any other drive letters previously assigned to the volume. 

If IOCTL_MOUNTMGR_CREATE_POINT specifies a drive letter, the drive letter must be upper case.

Note that a client can discover whether the mount manager has received the MOUNTDEV_MOUNTED_DEVICE_GUID device interface notification for its volume by querying the mount manager with <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

In this pseudocode sample, a mount manager client uses IOCTL_MOUNTMGR_CREATE_POINT to send the mount manager a device object name and its corresponding symbolic link:



## -syntax

````
    // The persistent symbolic link is a drive letter in
    // this case:
    wsprintf(dosBuffer, L"\\DosDevices\\%C:", DriveLetter);
    RtlInitUnicodeString(&dosName, dosBuffer);
    // The nonpersistent volume (device) object name is
    // formed using the volume number as a suffix
    wsprintf(ntBuffer, L"\\Device\\HarddiskVolume%D", 
                       Extension->VolumeNumber);
    RtlInitUnicodeString(&ntName, ntBuffer);
    createPointSize = sizeof(MOUNTMGR_CREATE_POINT_INPUT) +
                      dosName.Length + ntName.Length;
    // Allocate a header with length and offset information
    createPoint = (PMOUNTMGR_CREATE_POINT_INPUT)
                  ExAllocatePool(PagedPool, 
                  createPointSize);
    createPoint->SymbolicLinkNameOffset = 
                  sizeof(MOUNTMGR_CREATE_POINT_INPUT);
    createPoint->SymbolicLinkNameLength = dosName.Length;
    createPoint->DeviceNameOffset = 
        createPoint -> SymbolicLinkNameOffset +
        createPoint -> SymbolicLinkNameLength;
    createPoint->DeviceNameLength = ntName.Length;
    RtlCopyMemory((PCHAR) createPoint + 
                  createPoint -> SymbolicLinkNameOffset,
                  dosName.Buffer, dosName.Length);
    RtlCopyMemory((PCHAR) createPoint + 
                  createPoint->DeviceNameOffset,
                  ntName.Buffer, ntName.Length);
    // Use the name of the mount manager device object
    // defined in mountmgr.h (MOUNTMGR_DEVICE_NAME) to
    // obtain a pointer to the mount manager.
    RtlInitUnicodeString(&name, MOUNTMGR_DEVICE_NAME);
    status = IoGetDeviceObjectPointer(&name,
                              FILE_READ_ATTRIBUTES, 
                              &fileObject, &deviceObject);
    KeInitializeEvent(&event, NotificationEvent, FALSE);
    irp = IoBuildDeviceIoControlRequest(
            IOCTL_MOUNTMGR_CREATE_POINT,
            deviceObject, createPoint, createPointSize, 
            NULL, 0, FALSE, &event, &ioStatus);
    // Send the irp to the mount manager requesting
    // that a new mount point (persistent symbolic link)
    // be created for the indicated volume.
    status = IoCallDriver(deviceObject, irp);
````


## -ioctlparameters

### -input-buffer
The mount point manager places a header, defined as the structure <a href="..\mountmgr\ns-mountmgr-_mountmgr_create_point_input.md">MOUNTMGR_CREATE_POINT_INPUT</a> in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The mount manager inserts the newly-assigned persistent symbolic link name at the address pointed to by the <i>SymbolicLinkNameOffset</i> member of this structure, and it inserts the nonpersistent device name at the address pointed to by the <i>DeviceNameOffset</i> member of this structure. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_CREATE_POINT_INPUT).


### -output-buffer
None


### -output-buffer-length
None


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_CREATE_POINT_INPUT), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\mountmgr\ns-mountmgr-_mountmgr_create_point_input.md">MOUNTMGR_CREATE_POINT_INPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_CREATE_POINT control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

