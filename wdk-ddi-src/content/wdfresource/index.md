---
UID: NA:wdfresource
ms.assetid: ae262a83-02ac-307d-bec4-a4655f8a7524
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfresource.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfresource.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdfCmResourceListAppendDescriptor function](nf-wdfresource-wdfcmresourcelistappenddescriptor.md) | The WdfCmResourceListAppendDescriptor method adds a resource descriptor to the end of a specified resource list. |
| [WdfCmResourceListGetCount function](nf-wdfresource-wdfcmresourcelistgetcount.md) | The WdfCmResourceListGetCount method returns the number of resource descriptors that are contained in a specified resource list. |
| [WdfCmResourceListGetDescriptor function](nf-wdfresource-wdfcmresourcelistgetdescriptor.md) | The WdfCmResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a specified resource list. |
| [WdfCmResourceListInsertDescriptor function](nf-wdfresource-wdfcmresourcelistinsertdescriptor.md) | The WdfCmResourceListInsertDescriptor method inserts a resource descriptor into a specified resource list. |
| [WdfCmResourceListRemove function](nf-wdfresource-wdfcmresourcelistremove.md) | The WdfCmResourceListRemove method removes a resource descriptor from a specified resource list. |
| [WdfCmResourceListRemoveByDescriptor function](nf-wdfresource-wdfcmresourcelistremovebydescriptor.md) | The WdfCmResourceListRemoveByDescriptor method removes a specified resource descriptor from a specified resource list. |
| [WdfIoResourceListAppendDescriptor function](nf-wdfresource-wdfioresourcelistappenddescriptor.md) | The WdfIoResourceListAppendDescriptor method adds a resource descriptor to the end of a resource requirements list's logical configuration. |
| [WdfIoResourceListCreate function](nf-wdfresource-wdfioresourcelistcreate.md) | The WdfIoResourceListCreate method creates an empty logical configuration, which can be populated and added to a resource requirements list. |
| [WdfIoResourceListGetCount function](nf-wdfresource-wdfioresourcelistgetcount.md) | The WdfIoResourceListGetCount method returns the number of resource descriptors that are contained in a resource requirements list's logical configuration. |
| [WdfIoResourceListGetDescriptor function](nf-wdfresource-wdfioresourcelistgetdescriptor.md) | The WdfIoResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a resource requirements list's logical configuration. |
| [WdfIoResourceListInsertDescriptor function](nf-wdfresource-wdfioresourcelistinsertdescriptor.md) | The WdfIoResourceListInsertDescriptor method inserts a resource descriptor into a resource requirements list's logical configuration. |
| [WdfIoResourceListRemove function](nf-wdfresource-wdfioresourcelistremove.md) | The WdfIoResourceListRemove method removes a resource descriptor from a resource requirements list's logical configuration. |
| [WdfIoResourceListRemoveByDescriptor function](nf-wdfresource-wdfioresourcelistremovebydescriptor.md) | The WdfIoResourceListRemoveByDescriptor method removes a resource descriptor from a resource requirement list's logical configuration. |
| [WdfIoResourceListUpdateDescriptor function](nf-wdfresource-wdfioresourcelistupdatedescriptor.md) | The WdfIoResourceListUpdateDescriptor method updates a resource descriptor in a resource requirements list's logical configuration. |
| [WdfIoResourceRequirementsListAppendIoResList function](nf-wdfresource-wdfioresourcerequirementslistappendioreslist.md) | The WdfIoResourceRequirementsListAppendIoResList method adds a logical configuration to the end of a resource requirements list. |
| [WdfIoResourceRequirementsListGetCount function](nf-wdfresource-wdfioresourcerequirementslistgetcount.md) | The WdfIoResourceRequirementsListGetCount method returns the number of logical configurations that are contained in a resource requirements list. |
| [WdfIoResourceRequirementsListGetIoResList function](nf-wdfresource-wdfioresourcerequirementslistgetioreslist.md) | The WdfIoResourceRequirementsListGetIoResList method returns a handle to the framework resource-range-list object that represents a specified logical configuration in a specified resource requirements list. |
| [WdfIoResourceRequirementsListInsertIoResList function](nf-wdfresource-wdfioresourcerequirementslistinsertioreslist.md) | The WdfIoResourceRequirementsListInsertIoResList method inserts a logical configuration into a resource requirements list. |
| [WdfIoResourceRequirementsListRemove function](nf-wdfresource-wdfioresourcerequirementslistremove.md) | The WdfIoResourceRequirementsListRemove method removes a logical configuration from a resource requirements list. |
| [WdfIoResourceRequirementsListRemoveByIoResList function](nf-wdfresource-wdfioresourcerequirementslistremovebyioreslist.md) | The WdfIoResourceRequirementsListRemoveByIoResList method removes a logical configuration from a resource requirements list. |
| [WdfIoResourceRequirementsListSetInterfaceType function](nf-wdfresource-wdfioresourcerequirementslistsetinterfacetype.md) | The WdfIoResourceRequirementsListSetInterfaceType method assigns a bus type to a resource requirements list. |
| [WdfIoResourceRequirementsListSetSlotNumber function](nf-wdfresource-wdfioresourcerequirementslistsetslotnumber.md) | The WdfIoResourceRequirementsListSetSlotNumber method assigns a slot number to a resource requirements list. |
