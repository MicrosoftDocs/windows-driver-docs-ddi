---
UID: NA:d3dkmthk
ms.assetid: 8e950dfb-b94e-39e1-8e6d-9cc22344d42f
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# D3Dkmthk.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

D3Dkmthk.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [D3DKMTAcquireKeyedMutex function](nf-d3dkmthk-d3dkmtacquirekeyedmutex.md) | The D3DKMTAcquireKeyedMutex function acquires a keyed mutex object. |
| [D3DKMTAcquireKeyedMutex2 function](nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md) | Acquires a keyed mutex object that includes private data. |
| [D3DKMTChangeSurfacePointer function](nf-d3dkmthk-d3dkmtchangesurfacepointer.md) | The D3DKMTChangeSurfacePointer function is for system use only. |
| [D3DKMTCheckExclusiveOwnership function](nf-d3dkmthk-d3dkmtcheckexclusiveownership.md) | The D3DKMTCheckExclusiveOwnership function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources. |
| [D3DKMTCheckMonitorPowerState function](nf-d3dkmthk-d3dkmtcheckmonitorpowerstate.md) | The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor. |
| [D3DKMTCheckOcclusion function](nf-d3dkmthk-d3dkmtcheckocclusion.md) | The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded. |
| [D3DKMTCheckSharedResourceAccess function](nf-d3dkmthk-d3dkmtchecksharedresourceaccess.md) | The D3DKMTCheckSharedResourceAccess function determines if a process can access a shared resource. |
| [D3DKMTCheckVidPnExclusiveOwnership function](nf-d3dkmthk-d3dkmtcheckvidpnexclusiveownership.md) | The D3DKMTCheckVidPnExclusiveOwnership function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. |
| [D3DKMTCloseAdapter function](nf-d3dkmthk-d3dkmtcloseadapter.md) | The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function. |
| [D3DKMTConfigureSharedResource function](nf-d3dkmthk-d3dkmtconfiguresharedresource.md) | The D3DKMTConfigureSharedResource function configures a shared resource. |
| [D3DKMTCreateAllocation function](nf-d3dkmthk-d3dkmtcreateallocation.md) | The D3DKMTCreateAllocation function creates allocations of system or video memory. |
| [D3DKMTCreateAllocation2 function](nf-d3dkmthk-d3dkmtcreateallocation2.md) | Reserved for system use. Do not use in your driver. |
| [D3DKMTCreateBundleObject function](nf-d3dkmthk-d3dkmtcreatebundleobject.md) | Used to create a bundle object. |
| [D3DKMTCreateContext function](nf-d3dkmthk-d3dkmtcreatecontext.md) | The D3DKMTCreateContext function creates a kernel-mode device context. |
| [D3DKMTCreateContextVirtual function](nf-d3dkmthk-d3dkmtcreatecontextvirtual.md) | The D3DKMTCreateContextVirtual function creates a kernel mode device context that supports virtual addressing. |
| [D3DKMTCreateDCFromMemory function](nf-d3dkmthk-d3dkmtcreatedcfrommemory.md) | The D3DKMTCreateDCFromMemory function creates a display context from a specified block of memory. |
| [D3DKMTCreateDevice function](nf-d3dkmthk-d3dkmtcreatedevice.md) | The D3DKMTCreateDevice function creates a kernel-mode device context. |
| [D3DKMTCreateHwContext function](nf-d3dkmthk-d3dkmtcreatehwcontext.md) | Used to create a new hardware context. |
| [D3DKMTCreateHwQueue function](nf-d3dkmthk-d3dkmtcreatehwqueue.md) | Used to create a new hardware queue. |
| [D3DKMTCreateKeyedMutex function](nf-d3dkmthk-d3dkmtcreatekeyedmutex.md) | The D3DKMTCreateKeyedMutex function creates a keyed mutex object. |
| [D3DKMTCreateKeyedMutex2 function](nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md) | Creates a keyed mutex object that includes private data. |
| [D3DKMTCreateOverlay function](nf-d3dkmthk-d3dkmtcreateoverlay.md) | The D3DKMTCreateOverlay function creates a kernel-mode overlay object. |
| [D3DKMTCreatePagingQueue function](nf-d3dkmthk-d3dkmtcreatepagingqueue.md) | D3DKMTCreatePagingQueue is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident. |
| [D3DKMTCreateProtectedSession function](nf-d3dkmthk-d3dkmtcreateprotectedsession.md) | Used to create a protected session. |
| [D3DKMTCreateSynchronizationObject function](nf-d3dkmthk-d3dkmtcreatesynchronizationobject.md) | The D3DKMTCreateSynchronizationObject function creates a kernel-mode synchronization object. |
| [D3DKMTCreateSynchronizationObject2 function](nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md) | The D3DKMTCreateSynchronizationObject2 function creates a kernel-mode synchronization object. |
| [D3DKMTDestroyAllocation function](nf-d3dkmthk-d3dkmtdestroyallocation.md) | The D3DKMTDestroyAllocation function releases a resource, a list of allocations, or both. |
| [D3DKMTDestroyAllocation2 function](nf-d3dkmthk-d3dkmtdestroyallocation2.md) | The D3DKMTDestroyAllocation2 function releases a resource, a list of allocations, or both. |
| [D3DKMTDestroyContext function](nf-d3dkmthk-d3dkmtdestroycontext.md) | The D3DKMTDestroyContext function releases a kernel-mode device context. |
| [D3DKMTDestroyDCFromMemory function](nf-d3dkmthk-d3dkmtdestroydcfrommemory.md) | The D3DKMTDestroyDCFromMemory function releases the display context. |
| [D3DKMTDestroyDevice function](nf-d3dkmthk-d3dkmtdestroydevice.md) | The D3DKMTDestroyDevice function releases a kernel-mode device context. |
| [D3DKMTDestroyHwContext function](nf-d3dkmthk-d3dkmtdestroyhwcontext.md) | Used to destroy a hardware context. |
| [D3DKMTDestroyHwQueue function](nf-d3dkmthk-d3dkmtdestroyhwqueue.md) | Used to destroy a hardware queue. |
| [D3DKMTDestroyKeyedMutex function](nf-d3dkmthk-d3dkmtdestroykeyedmutex.md) | The D3DKMTDestroyKeyedMutex function destroys a keyed mutex object. |
| [D3DKMTDestroyOverlay function](nf-d3dkmthk-d3dkmtdestroyoverlay.md) | The D3DKMTDestroyOverlay function destroys a kernel-mode overlay object. |
| [D3DKMTDestroyPagingQueue function](nf-d3dkmthk-d3dkmtdestroypagingqueue.md) | D3DKMTDestroyPagingQueue waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object. |
| [D3DKMTDestroyProtectedSession function](nf-d3dkmthk-d3dkmtdestroyprotectedsession.md) | Used to destroy a protected session. |
| [D3DKMTDestroySynchronizationObject function](nf-d3dkmthk-d3dkmtdestroysynchronizationobject.md) | The D3DKMTDestroySynchronizationObject function destroys a kernel-mode synchronization object. |
| [D3DKMTEnumAdapters function](nf-d3dkmthk-d3dkmtenumadapters.md) | Enumerates all graphics adapters on the system. |
| [D3DKMTEscape function](nf-d3dkmthk-d3dkmtescape.md) | The D3DKMTEscape function exchanges information with the display miniport driver. |
| [D3DKMTEvict function](nf-d3dkmthk-d3dkmtevict.md) | D3DKMTEvict is used to decrement the allocation residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list. |
| [D3DKMTExtractBundleObject function](nf-d3dkmthk-d3dkmtextractbundleobject.md) | Used to extract the bundle object. |
| [D3DKMTFlipOverlay function](nf-d3dkmthk-d3dkmtflipoverlay.md) | The D3DKMTFlipOverlay function changes the allocation to display on the overlay. |
| [D3DKMTFreeGpuVirtualAddress function](nf-d3dkmthk-d3dkmtfreegpuvirtualaddress.md) | D3DKMTFreeGpuVirtualAddress releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped. |
| [D3DKMTGetContextInProcessSchedulingPriority function](nf-d3dkmthk-d3dkmtgetcontextinprocessschedulingpriority.md) | Called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts. |
| [D3DKMTGetContextSchedulingPriority function](nf-d3dkmthk-d3dkmtgetcontextschedulingpriority.md) | The D3DKMTGetContextSchedulingPriority function retrieves the scheduling priority for a device context. |
| [D3DKMTGetDeviceState function](nf-d3dkmthk-d3dkmtgetdevicestate.md) | The D3DKMTGetDeviceState function retrieves the state of a device. |
| [D3DKMTGetDisplayModeList function](nf-d3dkmthk-d3dkmtgetdisplaymodelist.md) | The D3DKMTGetDisplayModeList function retrieves a list of available display modes, including modes with extended format. |
| [D3DKMTGetMultisampleMethodList function](nf-d3dkmthk-d3dkmtgetmultisamplemethodlist.md) | The D3DKMTGetMultisampleMethodList function retrieves a list of multiple-sample methods that are used for an allocation. |
| [D3DKMTGetOverlayState function](nf-d3dkmthk-d3dkmtgetoverlaystate.md) | The D3DKMTGetOverlayState function retrieves the status about an overlay. |
| [D3DKMTGetPresentHistory function](nf-d3dkmthk-d3dkmtgetpresenthistory.md) | The D3DKMTGetPresentHistory function retrieves copying history. |
| [D3DKMTGetProcessDeviceLostSupport function](nf-d3dkmthk-d3dkmtgetprocessdevicelostsupport.md) | Used to get the indicated process. |
| [D3DKMTGetProcessSchedulingPriorityClass function](nf-d3dkmthk-d3dkmtgetprocessschedulingpriorityclass.md) | The D3DKMTGetProcessSchedulingPriorityClass function retrieves the scheduling priority for a process. |
| [D3DKMTGetRuntimeData function](nf-d3dkmthk-d3dkmtgetruntimedata.md) | The D3DKMTGetRuntimeData function is for system use only. |
| [D3DKMTGetScanLine function](nf-d3dkmthk-d3dkmtgetscanline.md) | The D3DKMTGetScanLine function determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line. |
| [D3DKMTGetSharedPrimaryHandle function](nf-d3dkmthk-d3dkmtgetsharedprimaryhandle.md) | The D3DKMTGetSharedPrimaryHandle function retrieves the global shared handle for the primary surface. |
| [D3DKMTGetSharedResourceAdapterLuid function](nf-d3dkmthk-d3dkmtgetsharedresourceadapterluid.md) | Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on. |
| [D3DKMTInvalidateActiveVidPn function](nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md) | The D3DKMTInvalidateActiveVidPn function invalidates the active video present network (VidPN) currently in use.Note   This function is obsolete in Windows 7 and later versions of the Windows operating systems. |
| [D3DKMTLock function](nf-d3dkmthk-d3dkmtlock.md) | The D3DKMTLock function locks an entire allocation or specific pages within an allocation. |
| [D3DKMTLock2 function](nf-d3dkmthk-d3dkmtlock2.md) | The D3DKMTLock2 function locks an entire allocation or specific pages within an allocation. |
| [D3DKMTMakeResident function](nf-d3dkmthk-d3dkmtmakeresident.md) | D3DKMTMakeResident is used to add a resource to the device residency list and increment the residency reference count on this allocation. |
| [D3DKMTMapGpuVirtualAddress function](nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md) | D3DKMTMapGpuVirtualAddress maps a graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state. |
| [D3DKMTOfferAllocations function](nf-d3dkmthk-d3dkmtofferallocations.md) | Offers video memory allocations for reuse. |
| [D3DKMTOpenAdapterFromDeviceName function](nf-d3dkmthk-d3dkmtopenadapterfromdevicename.md) | The D3DKMTOpenAdapterFromDeviceName function maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs. |
| [D3DKMTOpenAdapterFromGdiDisplayName function](nf-d3dkmthk-d3dkmtopenadapterfromgdidisplayname.md) | The D3DKMTOpenAdapterFromGdiDisplayName function maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs. |
| [D3DKMTOpenAdapterFromHdc function](nf-d3dkmthk-d3dkmtopenadapterfromhdc.md) | The D3DKMTOpenAdapterFromHdc function maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs. |
| [D3DKMTOpenAdapterFromLuid function](nf-d3dkmthk-d3dkmtopenadapterfromluid.md) | Maps a locally unique identifier (LUID) to a graphics adapter handle. |
| [D3DKMTOpenKeyedMutex function](nf-d3dkmthk-d3dkmtopenkeyedmutex.md) | The D3DKMTOpenKeyedMutex function opens a keyed mutex object. |
| [D3DKMTOpenKeyedMutex2 function](nf-d3dkmthk-d3dkmtopenkeyedmutex2.md) | Opens a keyed mutex object that includes private data. |
| [D3DKMTOpenNtHandleFromName function](nf-d3dkmthk-d3dkmtopennthandlefromname.md) | From a given graphics adapter name, opens an NT handle to the process. |
| [D3DKMTOpenProtectedSessionFromNtHandle function](nf-d3dkmthk-d3dkmtopenprotectedsessionfromnthandle.md) | Used to open a protected session from the NT handle. |
| [D3DKMTOpenResource function](nf-d3dkmthk-d3dkmtopenresource.md) | The D3DKMTOpenResource function opens a shared resource. |
| [D3DKMTOpenResource2 function](nf-d3dkmthk-d3dkmtopenresource2.md) | Reserved for system use. Do not use in your driver. |
| [D3DKMTOpenResourceFromNtHandle function](nf-d3dkmthk-d3dkmtopenresourcefromnthandle.md) | Opens a shared resource from an NT handle. |
| [D3DKMTOpenSyncObjectFromNtHandle function](nf-d3dkmthk-d3dkmtopensyncobjectfromnthandle.md) | Maps an NT process handle to a graphics processing unit (GPU) synchronization object. |
| [D3DKMTOpenSyncObjectFromNtHandle2 function](nf-d3dkmthk-d3dkmtopensyncobjectfromnthandle2.md) | D3DKMTOpenSyncObjectFromNtHandle2 opens a monitored fence object from an NT handle previously created by D3DKMTShareObjects. |
| [D3DKMTOpenSyncObjectNtHandleFromName function](nf-d3dkmthk-d3dkmtopensyncobjectnthandlefromname.md) | D3DKMTOpenSyncObjectNtHandleFromName opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations. |
| [D3DKMTOpenSynchronizationObject function](nf-d3dkmthk-d3dkmtopensynchronizationobject.md) | The D3DKMTOpenSynchronizationObject function opens a kernel-mode synchronization object. |
| [D3DKMTOutputDuplPresent function](nf-d3dkmthk-d3dkmtoutputduplpresent.md) | Submits a present command from the Desktop Duplication API swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys). |
| [D3DKMTOutputDuplReleaseFrame function](nf-d3dkmthk-d3dkmtoutputduplreleaseframe.md) | Indicates that the driver has finished processing the duplicated desktop image. |
| [D3DKMTPollDisplayChildren function](nf-d3dkmthk-d3dkmtpolldisplaychildren.md) | The D3DKMTPollDisplayChildren function queries for connectivity status of all child devices of the given adapter. |
| [D3DKMTPresent function](nf-d3dkmthk-d3dkmtpresent.md) | The D3DKMTPresent function submits a present command to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys). |
| [D3DKMTQueryAdapterInfo function](nf-d3dkmthk-d3dkmtqueryadapterinfo.md) | The D3DKMTQueryAdapterInfo function retrieves graphics adapter information. |
| [D3DKMTQueryAllocationResidency function](nf-d3dkmthk-d3dkmtqueryallocationresidency.md) | The D3DKMTQueryAllocationResidency function retrieves the residency status of a resource or list of allocations. |
| [D3DKMTQueryProtectedSessionInfoFromNtHandle function](nf-d3dkmthk-d3dkmtqueryprotectedsessioninfofromnthandle.md) | Used to get information on the protected session. |
| [D3DKMTQueryProtectedSessionStatus function](nf-d3dkmthk-d3dkmtqueryprotectedsessionstatus.md) | Used to query the status of the protected session. |
| [D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName function](nf-d3dkmthk-d3dkmtqueryremotevidpnsourcefromgdidisplayname.md) | Maps a GDI display name to a remote video present network (VidPN) source ID that is needed for a call to the D3DKMTOutputDuplPresent function. |
| [D3DKMTQueryResourceInfo function](nf-d3dkmthk-d3dkmtqueryresourceinfo.md) | The D3DKMTQueryResourceInfo function retrieves information about a shared resource. |
| [D3DKMTQueryResourceInfoFromNtHandle function](nf-d3dkmthk-d3dkmtqueryresourceinfofromnthandle.md) | Maps a global NT handle to resource information that is needed for a call to the D3DKMTQueryResourceInfo function. |
| [D3DKMTReclaimAllocations function](nf-d3dkmthk-d3dkmtreclaimallocations.md) | Reclaims video memory allocations. |
| [D3DKMTReclaimAllocations2 function](nf-d3dkmthk-d3dkmtreclaimallocations2.md) | D3DKMTReclaimAllocations2 reclaims video memory allocations. |
| [D3DKMTRegisterTrimNotification function](nf-d3dkmthk-d3dkmtregistertrimnotification.md) | D3DKMTRegisterTrimNotification is used by a kernel mode video memory manager to register and implement a callback for each kernel mode device to receive notifications from a graphics framework (such as OpenGL). |
| [D3DKMTReleaseKeyedMutex function](nf-d3dkmthk-d3dkmtreleasekeyedmutex.md) | The D3DKMTReleaseKeyedMutex function releases a keyed mutex object. |
| [D3DKMTReleaseKeyedMutex2 function](nf-d3dkmthk-d3dkmtreleasekeyedmutex2.md) | Releases a keyed mutex object that includes private data. |
| [D3DKMTReleaseProcessVidPnSourceOwners function](nf-d3dkmthk-d3dkmtreleaseprocessvidpnsourceowners.md) | The D3DKMTReleaseProcessVidPnSourceOwners function releases the video present network source owners for a process. |
| [D3DKMTRender function](nf-d3dkmthk-d3dkmtrender.md) | The D3DKMTRender function submits the current command buffer to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys). |
| [D3DKMTReserveGpuVirtualAddress function](nf-d3dkmthk-d3dkmtreservegpuvirtualaddress.md) | D3DKMTReserveGpuVirtualAddress reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it. |
| [D3DKMTSetAllocationPriority function](nf-d3dkmthk-d3dkmtsetallocationpriority.md) | The D3DKMTSetAllocationPriority function sets the priority level of a resource or list of allocations. |
| [D3DKMTSetContextInProcessSchedulingPriority function](nf-d3dkmthk-d3dkmtsetcontextinprocessschedulingpriority.md) | Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts. |
| [D3DKMTSetContextSchedulingPriority function](nf-d3dkmthk-d3dkmtsetcontextschedulingpriority.md) | The D3DKMTSetContextSchedulingPriority function sets the scheduling priority for a device context. |
| [D3DKMTSetDeviceLostSupport function](nf-d3dkmthk-d3dkmtsetdevicelostsupport.md) | Used to indicate that the device has lost support. |
| [D3DKMTSetDisplayMode function](nf-d3dkmthk-d3dkmtsetdisplaymode.md) | The D3DKMTSetDisplayMode function sets the allocation that is used to scan out to the display. |
| [D3DKMTSetDisplayPrivateDriverFormat function](nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat.md) | The D3DKMTSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source. |
| [D3DKMTSetGammaRamp function](nf-d3dkmthk-d3dkmtsetgammaramp.md) | The D3DKMTSetGammaRamp function sets the gamma ramp. |
| [D3DKMTSetMonitorColorSpaceTransform function](nf-d3dkmthk-d3dkmtsetmonitorcolorspacetransform.md) | Used to set the color space transform for the selected monitor. |
| [D3DKMTSetProcessSchedulingPriorityClass function](nf-d3dkmthk-d3dkmtsetprocessschedulingpriorityclass.md) | The D3DKMTSetProcessSchedulingPriorityClass function sets the scheduling priority for a process. |
| [D3DKMTSetQueuedLimit function](nf-d3dkmthk-d3dkmtsetqueuedlimit.md) | The D3DKMTSetQueuedLimit function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device. |
| [D3DKMTSetVidPnSourceOwner function](nf-d3dkmthk-d3dkmtsetvidpnsourceowner.md) | The D3DKMTSetVidPnSourceOwner function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN. |
| [D3DKMTSetVidPnSourceOwner1 function](nf-d3dkmthk-d3dkmtsetvidpnsourceowner1.md) | Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and lets output duplication options be specified. Supported starting with Windows 8. |
| [D3DKMTSetVidPnSourceOwner2 function](nf-d3dkmthk-d3dkmtsetvidpnsourceowner2.md) | Used to set the VidPN source owner. |
| [D3DKMTShareObjects function](nf-d3dkmthk-d3dkmtshareobjects.md) | Shares resource objects that were created with the D3DKMTCreateAllocation, D3DKMTCreateKeyedMutex2, and D3DKMTCreateSynchronizationObject2 functions. |
| [D3DKMTSharedPrimaryLockNotification function](nf-d3dkmthk-d3dkmtsharedprimarylocknotification.md) | The D3DKMTSharedPrimaryLockNotification function notifies the operating system about an upcoming lock to a shared primary surface. |
| [D3DKMTSharedPrimaryUnLockNotification function](nf-d3dkmthk-d3dkmtsharedprimaryunlocknotification.md) | The D3DKMTSharedPrimaryUnLockNotification function notifies the operating system that a shared primary surface was unlocked. |
| [D3DKMTSignalSynchronizationObject function](nf-d3dkmthk-d3dkmtsignalsynchronizationobject.md) | The D3DKMTSignalSynchronizationObject function inserts a signal for the specified synchronization objects in the specified context stream. |
| [D3DKMTSignalSynchronizationObject2 function](nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md) | The D3DKMTSignalSynchronizationObject2 function inserts a signal for the specified synchronization objects in the specified context stream. |
| [D3DKMTSignalSynchronizationObjectFromCpu function](nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu.md) | D3DKMTSignalSynchronizationObjectFromCpu enables a driver to signal a monitored fence.D3DKMTSignalSynchronizationObjectFromCpu enables a driver to signal a monitored fence. |
| [D3DKMTSignalSynchronizationObjectFromGpu function](nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu.md) | D3DKMTSignalSynchronizationObjectFromGpu is used to signal a monitored fence. |
| [D3DKMTSignalSynchronizationObjectFromGpu2 function](nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md) | D3DKMTSignalSynchronizationObjectFromGpu2 is used to signal a monitored fence. |
| [D3DKMTSubmitCommand function](nf-d3dkmthk-d3dkmtsubmitcommand.md) | D3DKMTSubmitCommand is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing. |
| [D3DKMTSubmitCommandToHwQueue function](nf-d3dkmthk-d3dkmtsubmitcommandtohwqueue.md) | Used to submit a command to the hardware queue. |
| [D3DKMTSubmitSignalSyncObjectsToHwQueue function](nf-d3dkmthk-d3dkmtsubmitsignalsyncobjectstohwqueue.md) | Used to submit a signal to the hardware queue. |
| [D3DKMTSubmitWaitForSyncObjectsToHwQueue function](nf-d3dkmthk-d3dkmtsubmitwaitforsyncobjectstohwqueue.md) | Used to submit a wait to the hardware queue. |
| [D3DKMTUnlock function](nf-d3dkmthk-d3dkmtunlock.md) | The D3DKMTUnlock function unlocks a list of allocations. |
| [D3DKMTUnlock2 function](nf-d3dkmthk-d3dkmtunlock2.md) | The D3DKMTUnlock2 function unlocks a list of allocations. |
| [D3DKMTUnregisterTrimNotification function](nf-d3dkmthk-d3dkmtunregistertrimnotification.md) | D3DKMTUnregisterTrimNotification is used to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL). |
| [D3DKMTUpdateGpuVirtualAddress function](nf-d3dkmthk-d3dkmtupdategpuvirtualaddress.md) | D3DKMTUpdateGpuVirtualAddress is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. |
| [D3DKMTUpdateOverlay function](nf-d3dkmthk-d3dkmtupdateoverlay.md) | The D3DKMTUpdateOverlay function modifies a kernel-mode overlay object. |
| [D3DKMTWaitForIdle function](nf-d3dkmthk-d3dkmtwaitforidle.md) | The D3DKMTWaitForIdle function waits for a display device to be idle. |
| [D3DKMTWaitForSynchronizationObject function](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject.md) | The D3DKMTWaitForSynchronizationObject function inserts a wait for the specified synchronization objects in the specified context stream. |
| [D3DKMTWaitForSynchronizationObject2 function](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md) | The D3DKMTWaitForSynchronizationObject2 function inserts a wait for the specified synchronization objects in the specified context stream. |
| [D3DKMTWaitForSynchronizationObjectFromCpu function](nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromcpu.md) | D3DKMTWaitForSynchronizationObjectFromCpu waits for a monitored fence to reach a certain value. |
| [D3DKMTWaitForSynchronizationObjectFromGpu function](nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromgpu.md) | D3DKMTWaitForSynchronizationObjectFromGpu waits for a monitored fence to reach a certain value before processing subsequent context commands. |
| [D3DKMTWaitForVerticalBlankEvent function](nf-d3dkmthk-d3dkmtwaitforverticalblankevent.md) | The D3DKMTWaitForVerticalBlankEvent function waits for the vertical blanking interval to occur and then returns. |
| [D3DKMTWaitForVerticalBlankEvent2 function](nf-d3dkmthk-d3dkmtwaitforverticalblankevent2.md) | Waits for specified wait objects, including a vertical blank event, to occur and then returns. Supported starting with Windows 8. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PDXGK_GRAPHICSPOWER_UNREGISTER callback](nc-d3dkmthk-pdxgk_graphicspower_unregister.md) | A callback to un-register itself with the graphics driver. |
| [PDXGK_POWER_NOTIFICATION callback](nc-d3dkmthk-pdxgk_power_notification.md) | A callback providing notification that the graphics device will be undergoing a device power state transition. |
| [PDXGK_REMOVAL_NOTIFICATION callback](nc-d3dkmthk-pdxgk_removal_notification.md) | A callback indicating that the graphics device is being removed. |
| [PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback](nc-d3dkmthk-pdxgk_set_shared_power_component_state.md) | A callback to indicate whether the specified power component is active. |
| [PFND3DKMT_ACQUIREKEYEDMUTEX callback](nc-d3dkmthk-pfnd3dkmt_acquirekeyedmutex.md) | The D3DKMTAcquireKeyedMutex function acquires a keyed mutex object. |
| [PFND3DKMT_ACQUIREKEYEDMUTEX2 callback](nc-d3dkmthk-pfnd3dkmt_acquirekeyedmutex2.md) | Acquires a keyed mutex object that includes private data. |
| [PFND3DKMT_CHANGESURFACEPOINTER callback](nc-d3dkmthk-pfnd3dkmt_changesurfacepointer.md) | The D3DKMTChangeSurfacePointer function is for system use only. |
| [PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP callback](nc-d3dkmthk-pfnd3dkmt_checkexclusiveownership.md) | The D3DKMTCheckExclusiveOwnership function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources. |
| [PFND3DKMT_CHECKMONITORPOWERSTATE callback](nc-d3dkmthk-pfnd3dkmt_checkmonitorpowerstate.md) | The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor. |
| [PFND3DKMT_CHECKOCCLUSION callback](nc-d3dkmthk-pfnd3dkmt_checkocclusion.md) | The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded. |
| [PFND3DKMT_CHECKSHAREDRESOURCEACCESS callback](nc-d3dkmthk-pfnd3dkmt_checksharedresourceaccess.md) | The D3DKMTCheckSharedResourceAccess function determines if a process can access a shared resource. |
| [PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP callback](nc-d3dkmthk-pfnd3dkmt_checkvidpnexclusiveownership.md) | The D3DKMTCheckVidPnExclusiveOwnership function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. |
| [PFND3DKMT_CLOSEADAPTER callback](nc-d3dkmthk-pfnd3dkmt_closeadapter.md) | The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function. |
| [PFND3DKMT_CONFIGURESHAREDRESOURCE callback](nc-d3dkmthk-pfnd3dkmt_configuresharedresource.md) | The D3DKMTConfigureSharedResource function configures a shared resource. |
| [PFND3DKMT_CREATEALLOCATION callback](nc-d3dkmthk-pfnd3dkmt_createallocation.md) | The D3DKMTCreateAllocation function creates allocations of system or video memory. |
| [PFND3DKMT_CREATEALLOCATION2 callback](nc-d3dkmthk-pfnd3dkmt_createallocation2.md) | Reserved for system use. Do not use in your driver. |
| [PFND3DKMT_CREATECONTEXT callback](nc-d3dkmthk-pfnd3dkmt_createcontext.md) | The D3DKMTCreateContext function creates a kernel-mode device context. |
| [PFND3DKMT_CREATEDCFROMMEMORY callback](nc-d3dkmthk-pfnd3dkmt_createdcfrommemory.md) | The D3DKMTCreateDCFromMemory function creates a display context from a specified block of memory. |
| [PFND3DKMT_CREATEDEVICE callback](nc-d3dkmthk-pfnd3dkmt_createdevice.md) | The D3DKMTCreateDevice function creates a kernel-mode device context. |
| [PFND3DKMT_CREATEKEYEDMUTEX callback](nc-d3dkmthk-pfnd3dkmt_createkeyedmutex.md) | The D3DKMTCreateKeyedMutex function creates a keyed mutex object. |
| [PFND3DKMT_CREATEKEYEDMUTEX2 callback](nc-d3dkmthk-pfnd3dkmt_createkeyedmutex2.md) | Creates a keyed mutex object that includes private data. |
| [PFND3DKMT_ENUMADAPTERS callback](nc-d3dkmthk-pfnd3dkmt_enumadapters.md) | Enumerates all graphics adapters on the system. |
| [PFND3DKMT_GETRUNTIMEDATA callback](nc-d3dkmthk-pfnd3dkmt_getruntimedata.md) | The D3DKMTGetRuntimeData function is for system use only. |
| [PFND3DKMT_OFFERALLOCATIONS callback](nc-d3dkmthk-pfnd3dkmt_offerallocations.md) | Offers video memory allocations for reuse. |
| [PFND3DKMT_OPENKEYEDMUTEX2 callback](nc-d3dkmthk-pfnd3dkmt_openkeyedmutex2.md) | Opens a keyed mutex object that includes private data. |
| [PFND3DKMT_OPENNTHANDLEFROMNAME callback](nc-d3dkmthk-pfnd3dkmt_opennthandlefromname.md) | From a given graphics adapter name, opens an NT handle to the process. |
| [PFND3DKMT_OPENRESOURCEFROMNTHANDLE callback](nc-d3dkmthk-pfnd3dkmt_openresourcefromnthandle.md) | Opens a shared resource from an NT handle. |
| [PFND3DKMT_OUTPUTDUPLPRESENT callback](nc-d3dkmthk-pfnd3dkmt_outputduplpresent.md) | Submits a present command from the Desktop Duplication API swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys). |
| [PFND3DKMT_OUTPUTDUPLRELEASEFRAME callback](nc-d3dkmthk-pfnd3dkmt_outputduplreleaseframe.md) | Indicates that the driver has finished processing the duplicated desktop image. |
| [PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME callback](nc-d3dkmthk-pfnd3dkmt_queryremotevidpnsourcefromgdidisplayname.md) | Maps a GDI display name to a remote video present network (VidPN) source ID that is needed for a call to the D3DKMTOutputDuplPresent function. |
| [PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback](nc-d3dkmthk-pfnd3dkmt_queryresourceinfofromnthandle.md) | Maps a global NT handle to resource information that is needed for a call to the D3DKMTQueryResourceInfo function. |
| [PFND3DKMT_RECLAIMALLOCATIONS callback](nc-d3dkmthk-pfnd3dkmt_reclaimallocations.md) | Reclaims video memory allocations. |
| [PFND3DKMT_RELEASEKEYEDMUTEX2 callback](nc-d3dkmthk-pfnd3dkmt_releasekeyedmutex2.md) | Releases a keyed mutex object that includes private data. |
| [PFND3DKMT_SETVIDPNSOURCEOWNER1 callback](nc-d3dkmthk-pfnd3dkmt_setvidpnsourceowner1.md) | Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and lets output duplication options be specified. Supported starting with Windows 8. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_D3DKMDT_DISPLAYMODE_FLAGS structure](ns-d3dkmthk-_d3dkmdt_displaymode_flags.md) | The D3DKMDT_DISPLAYMODE_FLAGS structure identifies attributes of a display mode. |
| [_D3DKMT_ACQUIREKEYEDMUTEX structure](ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md) | The D3DKMT_ACQUIREKEYEDMUTEX structure describes a keyed mutex that the D3DKMTAcquireKeyedMutex function acquires. |
| [_D3DKMT_ACQUIREKEYEDMUTEX2 structure](ns-d3dkmthk-_d3dkmt_acquirekeyedmutex2.md) | Describes a keyed mutex object that the D3DKMTAcquireKeyedMutex2 function acquires that includes private data. |
| [_D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE structure](ns-d3dkmthk-_d3dkmt_activate_specific_diag_escape.md) | Indicates an escape type that is to be activated or deactivated. |
| [_D3DKMT_ADAPTERADDRESS structure](ns-d3dkmthk-_d3dkmt_adapteraddress.md) | The D3DKMT_ADAPTERADDRESS structure describes the physical location of the graphics adapter. |
| [_D3DKMT_ADAPTERINFO structure](ns-d3dkmthk-_d3dkmt_adapterinfo.md) | Supplies configuration information about a graphics adapter. |
| [_D3DKMT_ADAPTERREGISTRYINFO structure](ns-d3dkmthk-_d3dkmt_adapterregistryinfo.md) | The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter. |
| [_D3DKMT_ADAPTERTYPE structure](ns-d3dkmthk-_d3dkmt_adaptertype.md) | Specifies the type of display device that the graphics adapter supports. |
| [_D3DKMT_ADDSURFACETOSWAPCHAIN structure](ns-d3dkmthk-_d3dkmt_addsurfacetoswapchain.md) | Used to add a surface to the swapchain. |
| [_D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_bltmodel_presenthistorytoken.md) | The D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure identifies a bit-block transfer (bitblt) present-history operation. |
| [_D3DKMT_BRIGHTNESS_INFO structure](ns-d3dkmthk-_d3dkmt_brightness_info.md) | Contains information about the brightness of an integrated display panel. |
| [_D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS structure](ns-d3dkmthk-_d3dkmt_brightness_possible_levels.md) | Contains information about all possible brightness levels that an integrated display panel supports. |
| [_D3DKMT_CHECKMONITORPOWERSTATE structure](ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate.md) | The D3DKMT_CHECKMONITORPOWERSTATE structure describes the connection to the monitor for which to check the power state. |
| [_D3DKMT_CHECKOCCLUSION structure](ns-d3dkmthk-_d3dkmt_checkocclusion.md) | The D3DKMT_CHECKOCCLUSION structure contains the handle to the window to check for occlusion. |
| [_D3DKMT_CHECKSHAREDRESOURCEACCESS structure](ns-d3dkmthk-_d3dkmt_checksharedresourceaccess.md) | The D3DKMT_CHECKSHAREDRESOURCEACCESS structure describes parameters that the D3DKMTCheckSharedResourceAccess function uses to determine if a process can access a shared resource. |
| [_D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure](ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership.md) | The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. |
| [_D3DKMT_CLOSEADAPTER structure](ns-d3dkmthk-_d3dkmt_closeadapter.md) | The D3DKMT_CLOSEADAPTER structure specifies the graphics adapter to close. |
| [_D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_composition_presenthistorytoken.md) | Identifies a composition swap chain present-history operation. This type of presentation is used for Extensible Application Markup Language (XAML)-based apps. |
| [_D3DKMT_CONFIGURESHAREDRESOURCE structure](ns-d3dkmthk-_d3dkmt_configuresharedresource.md) | The D3DKMT_CONFIGURESHAREDRESOURCE structure describes parameters that the D3DKMTConfigureSharedResource function uses to configure a shared resource. |
| [_D3DKMT_CREATEALLOCATION structure](ns-d3dkmthk-_d3dkmt_createallocation.md) | The D3DKMT_CREATEALLOCATION structure describes parameters for creating allocations. |
| [_D3DKMT_CREATEALLOCATIONFLAGS structure](ns-d3dkmthk-_d3dkmt_createallocationflags.md) | The D3DKMT_CREATEALLOCATIONFLAGS structure identifies how to create an allocation in a call to the D3DKMTCreateAllocation function. |
| [_D3DKMT_CREATEBUNDLEOBJECT structure](ns-d3dkmthk-_d3dkmt_createbundleobject.md) | Holds information to create a bundle object. |
| [_D3DKMT_CREATECONTEXT structure](ns-d3dkmthk-_d3dkmt_createcontext.md) | The D3DKMT_CREATECONTEXT structure describes a kernel-mode device context to create. |
| [_D3DKMT_CREATECONTEXTVIRTUAL structure](ns-d3dkmthk-_d3dkmt_createcontextvirtual.md) | D3DKMT_CREATECONTEXTVIRTUAL is used with D3DKMTCreateContextVirtual to create a kernel mode device context that supports virtual addressing. |
| [_D3DKMT_CREATEDCFROMMEMORY structure](ns-d3dkmthk-_d3dkmt_createdcfrommemory.md) | The D3DKMT_CREATEDCFROMMEMORY structure describes parameters for creating the display context. |
| [_D3DKMT_CREATEDEVICE structure](ns-d3dkmthk-_d3dkmt_createdevice.md) | The D3DKMT_CREATEDEVICE structure describes a kernel-mode device context. |
| [_D3DKMT_CREATEDEVICEFLAGS structure](ns-d3dkmthk-_d3dkmt_createdeviceflags.md) | The D3DKMT_CREATEDEVICEFLAGS structure identifies the type of device context to be created in a call to the D3DKMTCreateDevice function. |
| [_D3DKMT_CREATEHWCONTEXT structure](ns-d3dkmthk-_d3dkmt_createhwcontext.md) | A structure holding information to create a hardware context. |
| [_D3DKMT_CREATEHWQUEUE structure](ns-d3dkmthk-_d3dkmt_createhwqueue.md) | A structure holding information to create a hardware queue. |
| [_D3DKMT_CREATEKEYEDMUTEX structure](ns-d3dkmthk-_d3dkmt_createkeyedmutex.md) | The D3DKMT_CREATEKEYEDMUTEX structure describes a keyed mutex that the D3DKMTCreateKeyedMutex function creates. |
| [_D3DKMT_CREATEKEYEDMUTEX2 structure](ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md) | Describes a keyed mutex that the D3DKMTCreateKeyedMutex2 function creates that includes private data. |
| [_D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure](ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md) | Indicates how a handle to a keyed mutex is specified. |
| [_D3DKMT_CREATEOVERLAY structure](ns-d3dkmthk-_d3dkmt_createoverlay.md) | The D3DKMT_CREATEOVERLAY structure describes overlay hardware. |
| [_D3DKMT_CREATEPAGINGQUEUE structure](ns-d3dkmthk-_d3dkmt_createpagingqueue.md) | D3DKMT_CREATEPAGINGQUEUE is used with D3DKMTCreatePagingQueue to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident. |
| [_D3DKMT_CREATEPROTECTEDSESSION structure](ns-d3dkmthk-_d3dkmt_createprotectedsession.md) | Used to create a protected session. |
| [_D3DKMT_CREATESTANDARDALLOCATION structure](ns-d3dkmthk-_d3dkmt_createstandardallocation.md) | Used to create a standard allocation. |
| [_D3DKMT_CREATESTANDARDALLOCATIONFLAGS structure](ns-d3dkmthk-_d3dkmt_createstandardallocationflags.md) | Used to create standard allocation flags. |
| [_D3DKMT_CREATESYNCHRONIZATIONOBJECT structure](ns-d3dkmthk-_d3dkmt_createsynchronizationobject.md) | The D3DKMT_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTCreateSynchronizationObject function creates. |
| [_D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure](ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md) | The D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure describes a synchronization object that the D3DKMTCreateSynchronizationObject2 function creates. |
| [_D3DKMT_CURRENTDISPLAYMODE structure](ns-d3dkmthk-_d3dkmt_currentdisplaymode.md) | The D3DKMT_CURRENTDISPLAYMODE structure describes the current display mode of the specified video source. |
| [_D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure](ns-d3dkmthk-_d3dkmt_debug_snapshot_escape.md) | Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only. The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the D3DKMTEscape function. |
| [_D3DKMT_DESTROYALLOCATION structure](ns-d3dkmthk-_d3dkmt_destroyallocation.md) | The D3DKMT_DESTROYALLOCATION structure describes parameters for releasing allocations. |
| [_D3DKMT_DESTROYALLOCATION2 structure](ns-d3dkmthk-_d3dkmt_destroyallocation2.md) | The D3DKMT_DESTROYALLOCATION2 structure describes parameters for releasing allocations with D3DKMTDestroyAllocation2. |
| [_D3DKMT_DESTROYCONTEXT structure](ns-d3dkmthk-_d3dkmt_destroycontext.md) | The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release. |
| [_D3DKMT_DESTROYDCFROMMEMORY structure](ns-d3dkmthk-_d3dkmt_destroydcfrommemory.md) | The D3DKMT_DESTROYDCFROMMEMORY structure describes parameters for releasing the display context. |
| [_D3DKMT_DESTROYDEVICE structure](ns-d3dkmthk-_d3dkmt_destroydevice.md) | The D3DKMT_DESTROYDEVICE structure contains a handle to the kernel-mode device context to release. |
| [_D3DKMT_DESTROYHWCONTEXT structure](ns-d3dkmthk-_d3dkmt_destroyhwcontext.md) | A structure holding information to destroy a hardware context. |
| [_D3DKMT_DESTROYHWQUEUE structure](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) | A structure holding information to destroy a hardware queue. |
| [_D3DKMT_DESTROYKEYEDMUTEX structure](ns-d3dkmthk-_d3dkmt_destroykeyedmutex.md) | The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the D3DKMTDestroyKeyedMutex function destroys. |
| [_D3DKMT_DESTROYOVERLAY structure](ns-d3dkmthk-_d3dkmt_destroyoverlay.md) | The D3DKMT_DESTROYOVERLAY structure contains the handle to the overlay to destroy. |
| [_D3DKMT_DESTROYPROTECTEDSESSION structure](ns-d3dkmthk-_d3dkmt_destroyprotectedsession.md) | Holds information to destroy a protected session. |
| [_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure](ns-d3dkmthk-_d3dkmt_destroysynchronizationobject.md) | The D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy. |
| [_D3DKMT_DEVICEPRESENT_QUEUE_STATE structure](ns-d3dkmthk-_d3dkmt_devicepresent_queue_state.md) | A structure that holds information on the queue state of a hardware device. |
| [_D3DKMT_DEVICEPRESENT_STATE structure](ns-d3dkmthk-_d3dkmt_devicepresent_state.md) | The D3DKMT_DEVICEPRESENT_STATE structure describes parameters for retrieving the present status for a device. |
| [_D3DKMT_DEVICERESET_STATE structure](ns-d3dkmthk-_d3dkmt_devicereset_state.md) | The D3DKMT_DEVICERESET_STATE structure identifies reset status. |
| [_D3DKMT_DEVICE_ESCAPE structure](ns-d3dkmthk-_d3dkmt_device_escape.md) | Do not use the D3DKMT_DEVICE_ESCAPE structure or D3DKMT_DEVICEESCAPE_TYPE enumeration. They are for testing purposes only. The D3DKMT_DEVICE_ESCAPE structure describes how to control the display device in a call to the D3DKMTEscape function. |
| [_D3DKMT_DIRECTFLIP_SUPPORT structure](ns-d3dkmthk-_d3dkmt_directflip_support.md) | Indicates whether the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager (DWM) managed primary allocations. |
| [_D3DKMT_DIRTYREGIONS structure](ns-d3dkmthk-_d3dkmt_dirtyregions.md) | The D3DKMT_DIRTYREGIONS structure describes active rectangles (dirty regions) of a surface. |
| [_D3DKMT_DISPLAYMODE structure](ns-d3dkmthk-_d3dkmt_displaymode.md) | The D3DKMT_DISPLAYMODE structure describes a display mode. |
| [_D3DKMT_DISPLAYMODELIST structure](ns-d3dkmthk-_d3dkmt_displaymodelist.md) | Describes a list of display modes. |
| [_D3DKMT_DMM_ESCAPE structure](ns-d3dkmthk-_d3dkmt_dmm_escape.md) | Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only. The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the D3DKMTEscape function. |
| [_D3DKMT_ENUMADAPTERS structure](ns-d3dkmthk-_d3dkmt_enumadapters.md) | Supplies information for enumerating all graphics adapters on the system. |
| [_D3DKMT_ESCAPE structure](ns-d3dkmthk-_d3dkmt_escape.md) | The D3DKMT_ESCAPE structure describes information that is exchanged with the display miniport driver. |
| [_D3DKMT_EVICT structure](ns-d3dkmthk-_d3dkmt_evict.md) | D3DKMT_EVICT is used with D3DKMTEvict to subtract one from the residency reference count. |
| [_D3DKMT_EXTRACTBUNDLEOBJECT structure](ns-d3dkmthk-_d3dkmt_extractbundleobject.md) | Used to extract the bundle object. |
| [_D3DKMT_FENCE_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_fence_presenthistorytoken.md) | The D3DKMT_FENCE_PRESENTHISTORYTOKEN structure identifies a fence present-history operation. |
| [_D3DKMT_FLIPINFOFLAGS structure](ns-d3dkmthk-_d3dkmt_flipinfoflags.md) | The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function. |
| [_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytoken.md) | The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN structure identifies a flip present-history operation. |
| [_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure](ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytokenflags.md) | The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure identifies attributes of a flip present-history operation. |
| [_D3DKMT_FLIPOVERLAY structure](ns-d3dkmthk-_d3dkmt_flipoverlay.md) | The D3DKMT_FLIPOVERLAY structure describes a new allocation to display for the overlay. |
| [_D3DKMT_FLIPQUEUEINFO structure](ns-d3dkmthk-_d3dkmt_flipqueueinfo.md) | The D3DKMT_FLIPQUEUEINFO structure describes information about the graphics adapter's queue of flip operations that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function. |
| [_D3DKMT_FREEGPUVIRTUALADDRESS structure](ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md) | D3DKMT_FREEGPUVIRTUALADDRESS is used with FreeGpuVirtualAddress to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped. |
| [_D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_gdimodel_presenthistorytoken.md) | The D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure identifies a GDI present-history operation. |
| [_D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_gdimodel_sysmem_presenthistorytoken.md) | The D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure identifies a GDI system present-history operation. |
| [_D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure](ns-d3dkmthk-_d3dkmt_getcontextinprocessschedulingpriority.md) | Describes information that is required for an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts. |
| [_D3DKMT_GETCONTEXTSCHEDULINGPRIORITY structure](ns-d3dkmthk-_d3dkmt_getcontextschedulingpriority.md) | The D3DKMT_GETDEVICESCHEDULINGPRIORITY structure describes parameters for retrieving scheduling priority for a device context. |
| [_D3DKMT_GETDEVICESTATE structure](ns-d3dkmthk-_d3dkmt_getdevicestate.md) | The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device. |
| [_D3DKMT_GETDISPLAYMODELIST structure](ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md) | The D3DKMT_GETDISPLAYMODELIST structure describes a list of display modes. |
| [_D3DKMT_GETMULTISAMPLEMETHODLIST structure](ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md) | The D3DKMT_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation. |
| [_D3DKMT_GETOVERLAYSTATE structure](ns-d3dkmthk-_d3dkmt_getoverlaystate.md) | The D3DKMT_GETOVERLAYSTATE structure describes parameters that the D3DKMTGetOverlayState function uses to retrieve status about an overlay. |
| [_D3DKMT_GETPRESENTHISTORY structure](ns-d3dkmthk-_d3dkmt_getpresenthistory.md) | The D3DKMT_GETPRESENTHISTORY structure describes the state of copying history. |
| [_D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure](ns-d3dkmthk-_d3dkmt_getprocessdevicelostsupport.md) | Used to get the indicated process. |
| [_D3DKMT_GETSCANLINE structure](ns-d3dkmthk-_d3dkmt_getscanline.md) | The D3DKMT_GETSCANLINE structure contains information about a video present source's vertical blanking status. |
| [_D3DKMT_GETSHAREDPRIMARYHANDLE structure](ns-d3dkmthk-_d3dkmt_getsharedprimaryhandle.md) | The D3DKMT_GETSHAREDPRIMARYHANDLE structure describes the parameters that are required to retrieve the global shared handle for the primary surface. |
| [_D3DKMT_GETSHAREDRESOURCEADAPTERLUID structure](ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid.md) | Provides information that describes a shared resource and the graphics adapter that the resource was created on. |
| [_D3DKMT_INVALIDATEACTIVEVIDPN structure](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md) | The D3DKMT_INVALIDATEACTIVEVIDPN structure describes parameters that invalidate the active video present network (VidPN) currently in use. |
| [_D3DKMT_LOCK structure](ns-d3dkmthk-_d3dkmt_lock.md) | The D3DKMT_LOCK structure describes parameters for locking an allocation. |
| [_D3DKMT_LOCK2 structure](ns-d3dkmthk-_d3dkmt_lock2.md) | D3DKMT_LOCK2 describes parameters for locking an allocation. |
| [_D3DKMT_MPO3DDI_SUPPORT structure](ns-d3dkmthk-_d3dkmt_mpo3ddi_support.md) | A structure that holds the support status. |
| [_D3DKMT_MULTISAMPLEMETHOD structure](ns-d3dkmthk-_d3dkmt_multisamplemethod.md) | The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method. |
| [_D3DKMT_OFFERALLOCATIONS structure](ns-d3dkmthk-_d3dkmt_offerallocations.md) | Defines the video memory allocations that the driver offers for reuse. Used with the D3DKMTOfferAllocations function. |
| [_D3DKMT_OPENADAPTERFROMDEVICENAME structure](ns-d3dkmthk-_d3dkmt_openadapterfromdevicename.md) | The D3DKMT_OPENADAPTERFROMDEVICENAME structure describes the mapping of the given name of a device to a graphics adapter handle and monitor output. |
| [_D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure](ns-d3dkmthk-_d3dkmt_openadapterfromgdidisplayname.md) | The D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure describes the mapping of the given name of a GDI device to a graphics adapter handle and monitor output. |
| [_D3DKMT_OPENADAPTERFROMHDC structure](ns-d3dkmthk-_d3dkmt_openadapterfromhdc.md) | The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output. |
| [_D3DKMT_OPENADAPTERFROMLUID structure](ns-d3dkmthk-_d3dkmt_openadapterfromluid.md) | Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle. |
| [_D3DKMT_OPENGLINFO structure](ns-d3dkmthk-_d3dkmt_openglinfo.md) | The D3DKMT_OPENGLINFO structure describes OpenGL installable client driver (ICD) information. |
| [_D3DKMT_OPENKEYEDMUTEX structure](ns-d3dkmthk-_d3dkmt_openkeyedmutex.md) | The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the D3DKMTOpenKeyedMutex function opens. |
| [_D3DKMT_OPENKEYEDMUTEX2 structure](ns-d3dkmthk-_d3dkmt_openkeyedmutex2.md) | Describes a keyed mutex that the D3DKMTOpenKeyedMutex2 function opens. |
| [_D3DKMT_OPENNTHANDLEFROMNAME structure](ns-d3dkmthk-_d3dkmt_opennthandlefromname.md) | Describes information that is required to open an NT handle to the process from a graphics adapter name. |
| [_D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE structure](ns-d3dkmthk-_d3dkmt_openprotectedsessionfromnthandle.md) | Used to open a protected session from the NT handle. |
| [_D3DKMT_OPENRESOURCE structure](ns-d3dkmthk-_d3dkmt_openresource.md) | The D3DKMT_OPENRESOURCE structure describes parameters for opening a resource. |
| [_D3DKMT_OPENRESOURCEFROMNTHANDLE structure](ns-d3dkmthk-_d3dkmt_openresourcefromnthandle.md) | Describes information that is required to open a shared resource from an NT handle to the process. The shared resource can be a set of allocations, a keyed mutex, or a synchronization object. |
| [_D3DKMT_OPENSYNCHRONIZATIONOBJECT structure](ns-d3dkmthk-_d3dkmt_opensynchronizationobject.md) | The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTOpenSynchronizationObject function opens. |
| [_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure](ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md) | Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object. |
| [_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 structure](ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle2.md) | D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 is used with D3DKMTOpenSyncObjectFromNtHandle2 to open a monitored fence object. |
| [_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME structure](ns-d3dkmthk-_d3dkmt_opensyncobjectnthandlefromname.md) | D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME is used with D3DKMTOpenSyncObjectNtHandleFromName to open an NT handle for a named shared monitored fence object. |
| [_D3DKMT_OUTPUTDUPLCONTEXTSCOUNT structure](ns-d3dkmthk-_d3dkmt_outputduplcontextscount.md) | Specifies the number of current Desktop Duplication API (DDA) clients that are attached to a given video present network (VidPN). |
| [_D3DKMT_OUTPUTDUPLPRESENT structure](ns-d3dkmthk-_d3dkmt_outputduplpresent.md) | Describes a Desktop Duplication API swapchain present operation. |
| [_D3DKMT_OUTPUTDUPLPRESENTFLAGS structure](ns-d3dkmthk-_d3dkmt_outputduplpresentflags.md) | Describes options for a Desktop Duplication API swapchain present operation. |
| [_D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure](ns-d3dkmthk-_d3dkmt_outputdupl_release_frame.md) | Defines the duplicated desktop image that is to be released in a call to the D3DKMTOutputDuplReleaseFrame function. |
| [_D3DKMT_OUTPUTDUPL_SNAPSHOT structure](ns-d3dkmthk-_d3dkmt_outputdupl_snapshot.md) | Provides information on the current processes in which output duplication is occurring. |
| [_D3DKMT_POLLDISPLAYCHILDREN structure](ns-d3dkmthk-_d3dkmt_polldisplaychildren.md) | The D3DKMT_POLLDISPLAYCHILDREN structure describes parameters for querying for connectivity status of all child devices of the given display adapter. |
| [_D3DKMT_PRESENT structure](ns-d3dkmthk-_d3dkmt_present.md) | The D3DKMT_PRESENT structure describes the present operation. |
| [_D3DKMT_PRESENTFLAGS structure](ns-d3dkmthk-_d3dkmt_presentflags.md) | The D3DKMT_PRESENTFLAGS structure identifies how to perform a present operation. |
| [_D3DKMT_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_presenthistorytoken.md) | The D3DKMT_PRESENTHISTORYTOKEN structure identifies a type of present operation. |
| [_D3DKMT_PRESENT_REDIRECTED structure](ns-d3dkmthk-_d3dkmt_present_redirected.md) | Used to give information on the status of the present history token. |
| [_D3DKMT_PRESENT_RGNS structure](ns-d3dkmthk-_d3dkmt_present_rgns.md) | Specifies dirty and move regions in a present operation. |
| [_D3DKMT_PRESENT_STATS structure](ns-d3dkmthk-_d3dkmt_present_stats.md) | The D3DKMT_PRESENT_STATS structure describes present status for a rendering device. |
| [_D3DKMT_QUERYADAPTERINFO structure](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) | The D3DKMT_QUERYADAPTERINFO structure contains information that describes the graphics adapter. |
| [_D3DKMT_QUERYALLOCATIONRESIDENCY structure](ns-d3dkmthk-_d3dkmt_queryallocationresidency.md) | The D3DKMT_QUERYALLOCATIONRESIDENCY structure describes information for retrieving the residency status from a resource or list of allocations. |
| [_D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE structure](ns-d3dkmthk-_d3dkmt_queryprotectedsessioninfofromnthandle.md) | Used to query information on the protected session. |
| [_D3DKMT_QUERYPROTECTEDSESSIONSTATUS structure](ns-d3dkmthk-_d3dkmt_queryprotectedsessionstatus.md) | Used to query the status of the protected session. |
| [_D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure](ns-d3dkmthk-_d3dkmt_queryremotevidpnsourcefromgdidisplayname.md) | Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID. |
| [_D3DKMT_QUERYRESOURCEINFO structure](ns-d3dkmthk-_d3dkmt_queryresourceinfo.md) | The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource. |
| [_D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure](ns-d3dkmthk-_d3dkmt_queryresourceinfofromnthandle.md) | Describes information that is required to map a global NT handle to resource information. |
| [_D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure](ns-d3dkmthk-_d3dkmt_query_physical_adapter_pnp_key.md) | A structure that holds information to query the physical adapter PNP key. |
| [_D3DKMT_RECLAIMALLOCATIONS structure](ns-d3dkmthk-_d3dkmt_reclaimallocations.md) | Describes video memory resources that are to be reclaimed and that the driver previously offered for reuse. Used with the D3DKMTReclaimAllocations function. |
| [_D3DKMT_RECLAIMALLOCATIONS2 structure](ns-d3dkmthk-_d3dkmt_reclaimallocations2.md) | D3DKMT_RECLAIMALLOCATIONS2 describes video memory resources that are to be reclaimed and that the driver previously offered for reuse. Used with the D3DKMTReclaimAllocations2 function. |
| [_D3DKMT_REGISTERTRIMNOTIFICATION structure](ns-d3dkmthk-_d3dkmt_registertrimnotification.md) | D3DKMT_REGISTERTRIMNOTIFICATION is used with D3DKMTRegisterTrimNotification to register a callback for a kernel mode device for notifications from a graphics framework (such as OpenGL). |
| [_D3DKMT_RELEASEKEYEDMUTEX structure](ns-d3dkmthk-_d3dkmt_releasekeyedmutex.md) | The D3DKMT_RELEASEKEYEDMUTEX structure describes a keyed mutex that the D3DKMTReleaseKeyedMutex function releases. |
| [_D3DKMT_RELEASEKEYEDMUTEX2 structure](ns-d3dkmthk-_d3dkmt_releasekeyedmutex2.md) | Describes a keyed mutex object that the D3DKMTReleaseKeyedMutex2 function releases that includes private data. |
| [_D3DKMT_REMOVESURFACEFROMSWAPCHAIN structure](ns-d3dkmthk-_d3dkmt_removesurfacefromswapchain.md) | Used to remove a surface from the swap chain. |
| [_D3DKMT_RENDER structure](ns-d3dkmthk-_d3dkmt_render.md) | The D3DKMT_RENDER structure describes the current command buffer to be rendered. |
| [_D3DKMT_RENDERFLAGS structure](ns-d3dkmthk-_d3dkmt_renderflags.md) | The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the D3DKMTRender function. |
| [_D3DKMT_SEGMENTGROUPSIZEINFO structure](ns-d3dkmthk-_d3dkmt_segmentgroupsizeinfo.md) | A structure that holds information about the segment group size. |
| [_D3DKMT_SEGMENTSIZEINFO structure](ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md) | The D3DKMT_SEGMENTSIZEINFO structure describes the size, in bytes, of memory and aperture segments. |
| [_D3DKMT_SETALLOCATIONPRIORITY structure](ns-d3dkmthk-_d3dkmt_setallocationpriority.md) | The D3DKMT_SETALLOCATIONPRIORITY structure describes the priority level to set a resource or list of allocations to. |
| [_D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY structure](ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority.md) | Describes parameters for an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts. |
| [_D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure](ns-d3dkmthk-_d3dkmt_setcontextschedulingpriority.md) | The D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure describes parameters for setting scheduling priority for a device context. |
| [_D3DKMT_SETDEVICELOSTSUPPORT structure](ns-d3dkmthk-_d3dkmt_setdevicelostsupport.md) | Used to indicate whether a device can recover from losing a graphics device. |
| [_D3DKMT_SETDISPLAYMODE structure](ns-d3dkmthk-_d3dkmt_setdisplaymode.md) | The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display. |
| [_D3DKMT_SETDISPLAYMODE_FLAGS structure](ns-d3dkmthk-_d3dkmt_setdisplaymode_flags.md) | The D3DKMT_SETDISPLAYMODE_FLAGS structure identifies attributes for setting the display mode. |
| [_D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure](ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat.md) | The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source. |
| [_D3DKMT_SETGAMMARAMP structure](ns-d3dkmthk-_d3dkmt_setgammaramp.md) | The D3DKMT_SETGAMMARAMP structure describes parameters for setting the gamma ramp. |
| [_D3DKMT_SETQUEUEDLIMIT structure](ns-d3dkmthk-_d3dkmt_setqueuedlimit.md) | The D3DKMT_SETQUEUEDLIMIT structure describes parameters for setting or retrieving the limit for the number of operations of the given type that can be queued for the given device. |
| [_D3DKMT_SETVIDPNSOURCEOWNER structure](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) | The D3DKMT_SETVIDPNSOURCEOWNER structure describes the parameters for setting or releasing the video present source in the path of a video present network (VidPN) topology that owns the VidPN. |
| [_D3DKMT_SETVIDPNSOURCEOWNER1 structure](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner1.md) | Describes the information, including output duplication options, needed to set or release the video present source in the path of a video present network (VidPN) topology that owns the VidPN. |
| [_D3DKMT_SETVIDPNSOURCEOWNER2 structure](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner2.md) | Used to set the VidPN source owner. |
| [_D3DKMT_SET_COLORSPACE_TRANSFORM structure](ns-d3dkmthk-_d3dkmt_set_colorspace_transform.md) | TBD. |
| [_D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md) | The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock. |
| [_D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure](ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md) | The D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure describes the shared primary surface that an application just unlocked. |
| [_D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure](ns-d3dkmthk-_d3dkmt_signalsynchronizationobject.md) | The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject function signals. |
| [_D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure](ns-d3dkmthk-_d3dkmt_signalsynchronizationobject2.md) | The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject2 function signals. |
| [_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromcpu.md) | D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTSignalSynchronizationObjectFromCpu to enable a driver to signal a monitored fence. |
| [_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu.md) | D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTSignalSynchronizationObjectFromGpu to signal a monitored fence. |
| [_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2.md) | D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 is used with D3DKMTSignalSynchronizationObjectFromGpu2 to signal a monitored fence. |
| [_D3DKMT_STANDARDALLOCATION_EXISTINGHEAP structure](ns-d3dkmthk-_d3dkmt_standardallocation_existingheap.md) | Holds information about the existing heap. |
| [_D3DKMT_SUBMITCOMMAND structure](ns-d3dkmthk-_d3dkmt_submitcommand.md) | The D3DKMT_SUBMITCOMMAND structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing. |
| [_D3DKMT_SUBMITCOMMANDTOHWQUEUE structure](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) | A structure that holds information to submit a command to the hardware queue. |
| [_D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure](ns-d3dkmthk-_d3dkmt_submitsignalsyncobjectstohwqueue.md) | A structure holding information to submit a signal to the hardware queue. |
| [_D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure](ns-d3dkmthk-_d3dkmt_submitwaitforsyncobjectstohwqueue.md) | A structure that contains information to submit a wait on the hardware queue. |
| [_D3DKMT_SURFACECOMPLETE_PRESENTHISTORYTOKEN structure](ns-d3dkmthk-_d3dkmt_surfacecomplete_presenthistorytoken.md) | A structure used to present the history token for a surface. |
| [_D3DKMT_TRIMNOTIFICATION structure](ns-d3dkmthk-_d3dkmt_trimnotification.md) | D3DKMT_TRIMNOTIFICATION is used to notify a driver to trim its memory residency list. |
| [_D3DKMT_UMDFILENAMEINFO structure](ns-d3dkmthk-_d3dkmt_umdfilenameinfo.md) | The D3DKMT_UMDFILENAMEINFO structure contains the name of an OpenGL ICD that is based on the specified version of the DirectX runtime. |
| [_D3DKMT_UMD_DRIVER_VERSION structure](ns-d3dkmthk-_d3dkmt_umd_driver_version.md) | Indicates the version number of the user-mode driver. |
| [_D3DKMT_UNLOCK structure](ns-d3dkmthk-_d3dkmt_unlock.md) | The D3DKMT_UNLOCK structure describes allocations to unlock. |
| [_D3DKMT_UNLOCK2 structure](ns-d3dkmthk-_d3dkmt_unlock2.md) | D3DKMT_UNLOCK2 describes an allocation to unlock. |
| [_D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure](ns-d3dkmthk-_d3dkmt_unorderedpresentswapchain.md) | Used to store information about the swapchain being presented. |
| [_D3DKMT_UNREGISTERTRIMNOTIFICATION structure](ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md) | D3DKMT_UNREGISTERTRIMNOTIFICATION is used with D3DKMTUnregisterTrimNotification to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL). |
| [_D3DKMT_UPDATEGPUVIRTUALADDRESS structure](ns-d3dkmthk-_d3dkmt_updategpuvirtualaddress.md) | D3DKMT_UPDATEGPUVIRTUALADDRESS is used with UpdateGpuVirtualAddress to allow the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. |
| [_D3DKMT_UPDATEOVERLAY structure](ns-d3dkmthk-_d3dkmt_updateoverlay.md) | The D3DKMT_UPDATEOVERLAY structure describes parameters for modifying an overlay. |
| [_D3DKMT_VIDMM_ESCAPE structure](ns-d3dkmthk-_d3dkmt_vidmm_escape.md) | The D3DKMT_VIDMM_ESCAPE structure describes how to control the video memory manager (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function. |
| [_D3DKMT_VIDPNSOURCEOWNER_FLAGS structure](ns-d3dkmthk-_d3dkmt_vidpnsourceowner_flags.md) | Specifies output duplication options for use with the D3DKMTSetVidPnSourceOwner1 function. |
| [_D3DKMT_VIDSCH_ESCAPE structure](ns-d3dkmthk-_d3dkmt_vidsch_escape.md) | The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function. |
| [_D3DKMT_WAITFORIDLE structure](ns-d3dkmthk-_d3dkmt_waitforidle.md) | The D3DKMT_WAITFORIDLE structure specifies a display device to wait for an idle condition. |
| [_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md) | The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject function waits for to occur. |
| [_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2.md) | The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject2 function waits for to occur. |
| [_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU structure](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu.md) | D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTWaitForSynchronizationObjectFromCpu to wait for a monitored fence to reach a certain value. |
| [_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu.md) | D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTWaitForSynchronizationObjectFromGpu to wait for a monitored fence to reach a certain value. |
| [_D3DKMT_WAITFORVERTICALBLANKEVENT structure](ns-d3dkmthk-_d3dkmt_waitforverticalblankevent.md) | The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur. |
| [_D3DKMT_WAITFORVERTICALBLANKEVENT2 structure](ns-d3dkmthk-_d3dkmt_waitforverticalblankevent2.md) | Describes parameters for multiple wait objects, including a vertical blank event. Supported starting with Windows 8. |
| [_D3DKMT_WORKINGSETFLAGS structure](ns-d3dkmthk-_d3dkmt_workingsetflags.md) | The D3DKMT_WORKINGSETFLAGS structure identifies working-set properties of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function. |
| [_D3DKMT_WORKINGSETINFO structure](ns-d3dkmthk-_d3dkmt_workingsetinfo.md) | The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function. |
| [_DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure](ns-d3dkmthk-_dxgk_graphicspower_register_input_v_1_1.md) | Used to register the power state of a new input. |
| [_DXGK_GRAPHICSPOWER_REGISTER_OUTPUT structure](ns-d3dkmthk-_dxgk_graphicspower_register_output.md) | A structure containing output data used to manage shared power components. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_D3DKMDT_MODE_PRUNING_REASON enumeration](ne-d3dkmthk-_d3dkmdt_mode_pruning_reason.md) | The D3DKMDT_MODE_PRUNING_REASON enumeration type contains values that identify the reason why the monitor either supports a display mode or does not support a display mode. |
| [_D3DKMT_BRIGHTNESS_INFO_TYPE enumeration](ne-d3dkmthk-_d3dkmt_brightness_info_type.md) | Indicates the type of information to retrieve or set for the brightness of an integrated display panel. |
| [_D3DKMT_DEVICEEXECUTION_STATE enumeration](ne-d3dkmthk-_d3dkmt_deviceexecution_state.md) | Contains values that indicate the execution status for a device. |
| [_D3DKMT_DEVICESTATE_TYPE enumeration](ne-d3dkmthk-_d3dkmt_devicestate_type.md) | The D3DKMT_DEVICESTATE_TYPE enumeration type contains values that indicate the status of a device. |
| [_D3DKMT_OFFER_PRIORITY enumeration](ne-d3dkmthk-_d3dkmt_offer_priority.md) | Indicates the importance of video memory resources that the user-mode display driver offers for reuse. |
| [_D3DKMT_PNP_KEY_TYPE enumeration](ne-d3dkmthk-_d3dkmt_pnp_key_type.md) | An enum that indicates the type of PNP key. |
| [_D3DKMT_PRESENT_MODEL enumeration](ne-d3dkmthk-_d3dkmt_present_model.md) | The D3DKMT_PRESENT_MODEL enumeration type contains values that indicate the model for a present operation. |
| [_D3DKMT_PROTECTED_SESSION_STATUS enumeration](ne-d3dkmthk-_d3dkmt_protected_session_status.md) | Indicates the status of the protected session. |
| [_D3DKMT_QUEUEDLIMIT_TYPE enumeration](ne-d3dkmthk-_d3dkmt_queuedlimit_type.md) | The D3DKMT_QUEUEDLIMIT_TYPE enumeration type contains values that indicate the type of operations to set or retrieve the queued limit for in a call to the D3DKMTSetQueuedLimit function. |
| [_D3DKMT_SCHEDULINGPRIORITYCLASS enumeration](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md) | The D3DKMT_SCHEDULINGPRIORITYCLASS enumeration type contains values that describe the scheduling priority for a process. |
| [_D3DKMT_STANDARDALLOCATIONTYPE enumeration](ne-d3dkmthk-_d3dkmt_standardallocationtype.md) | Used to give information on the allocation type. |
| [_D3DKMT_TDRDBGCTRLTYPE enumeration](ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md) | The D3DKMT_TDRDBGCTRLTYPE enumeration type contains values that affect the behavior of the operating system's Timeout Detection and Recovery (TDR) process in a call to the OpenGL D3DKMTEscape function. |
| [_D3DKMT_VIDMMESCAPETYPE enumeration](ne-d3dkmthk-_d3dkmt_vidmmescapetype.md) | The D3DKMT_VIDMMESCAPETYPE enumeration is used with the D3DKMT_VIDMM_ESCAPE structure. |
| [_D3DKMT_VIDSCHESCAPETYPE enumeration](ne-d3dkmthk-_d3dkmt_vidschescapetype.md) | The D3DKMT_VIDMMESCAPETYPE enumeration is used with the D3DKMT_VIDSCH_ESCAPE structure. |
| [_QAI_DRIVERVERSION enumeration](ne-d3dkmthk-_qai_driverversion.md) | The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports. |
