---
UID: TP:wdf
ms.assetid: cf4c7959-f8f4-3342-82e9-ced7b9f1b959
ms.author: windowsdriverdev
ms.date: 04/23/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Windows Driver Framework

## -description

Overview of the Windows Driver Framework technology.

To develop Windows Driver Framework, you need these headers:

 * [wdf.h](..\wdf\index.md)
 * [wdfassert.h](..\wdfassert\index.md)
 * [wdfbugcodes.h](..\wdfbugcodes\index.md)
 * [wdfchildlist.h](..\wdfchildlist\index.md)
 * [wdfcollection.h](..\wdfcollection\index.md)
 * [wdfcommonbuffer.h](..\wdfcommonbuffer\index.md)
 * [wdfcompanion.h](..\wdfcompanion\index.md)
 * [wdfcompaniontarget.h](..\wdfcompaniontarget\index.md)
 * [wdfcontrol.h](..\wdfcontrol\index.md)
 * [wdfcore.h](..\wdfcore\index.md)
 * [wdfdevice.h](..\wdfdevice\index.md)
 * [wdfdmaenabler.h](..\wdfdmaenabler\index.md)
 * [wdfdmatransaction.h](..\wdfdmatransaction\index.md)
 * [wdfdpc.h](..\wdfdpc\index.md)
 * [wdfdriver.h](..\wdfdriver\index.md)
 * [wdffdo.h](..\wdffdo\index.md)
 * [wdffileobject.h](..\wdffileobject\index.md)
 * [wdffuncenum.h](..\wdffuncenum\index.md)
 * [wdfhwaccess.h](..\wdfhwaccess\index.md)
 * [wdfinstaller.h](..\wdfinstaller\index.md)
 * [wdfinterrupt.h](..\wdfinterrupt\index.md)
 * [wdfio.h](..\wdfio\index.md)
 * [wdfiotarget.h](..\wdfiotarget\index.md)
 * [wdfmemory.h](..\wdfmemory\index.md)
 * [wdfminiport.h](..\wdfminiport\index.md)
 * [wdfobject.h](..\wdfobject\index.md)
 * [wdfpdo.h](..\wdfpdo\index.md)
 * [wdfqueryinterface.h](..\wdfqueryinterface\index.md)
 * [wdfregistry.h](..\wdfregistry\index.md)
 * [wdfrequest.h](..\wdfrequest\index.md)
 * [wdfresource.h](..\wdfresource\index.md)
 * [wdfstring.h](..\wdfstring\index.md)
 * [wdfsync.h](..\wdfsync\index.md)
 * [wdftimer.h](..\wdftimer\index.md)
 * [wdftriage.h](..\wdftriage\index.md)
 * [wdftypes.h](..\wdftypes\index.md)
 * [wdfusb.h](..\wdfusb\index.md)
 * [wdfverifier.h](..\wdfverifier\index.md)
 * [wdfwmi.h](..\wdfwmi\index.md)
 * [wdfworkitem.h](..\wdfworkitem\index.md)
 * [wudfddi.h](..\wudfddi\index.md)
 * [wudfddi_hwaccess.h](..\wudfddi_hwaccess\index.md)
 * [wudfddi_types.h](..\wudfddi_types\index.md)
 * [wudfdevice.h](..\wudfdevice\index.md)
 * [wudfinterrupt.h](..\wudfinterrupt\index.md)
 * [wudfusb.h](..\wudfusb\index.md)
 * [wudfwdm.h](..\wudfwdm\index.md)
 * [wudfworkitem.h](..\wudfworkitem\index.md)

For the programming guide, see [Windows Driver Framework](https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf).

The following table lists all of the Windows Driver Frameworks (WDF) callbacks, methods, and macros, and their availability in KMDF and UMDF version 2.

For a list of framework objects and mode availability, see [Summary of Framework Objects](https://docs.microsoft.com/windows-hardware/drivers/wdf/summary-of-framework-objects).

|Name|Minimum KMDF Version|Minimum UMDF Version|
|--- |--- |--- |
|[_EvtChildListAddressDescriptionCleanup_](https://msdn.microsoft.com/library/windows/hardware/ff540823)|1.0|
|[_EvtChildListAddressDescriptionCopy_](https://msdn.microsoft.com/library/windows/hardware/ff540824)|1.0|
|[_EvtChildListAddressDescriptionDuplicate_](https://msdn.microsoft.com/library/windows/hardware/ff540826)|1.0|
|[_EvtChildListCreateDevice_](https://msdn.microsoft.com/library/windows/hardware/ff540828)|1.0|
|[_EvtChildListDeviceReenumerated_](https://msdn.microsoft.com/library/windows/hardware/ff540830)|1.0|
|[_EvtChildListIdentificationDescriptionCleanup_](https://msdn.microsoft.com/library/windows/hardware/ff540832)|1.0|
|[_EvtChildListIdentificationDescriptionCompare_](https://msdn.microsoft.com/library/windows/hardware/ff540833)|1.0|
|[_EvtChildListIdentificationDescriptionCopy_](https://msdn.microsoft.com/library/windows/hardware/ff540834)|1.0|
|[_EvtChildListIdentificationDescriptionDuplicate_](https://msdn.microsoft.com/library/windows/hardware/ff540836)|1.0|
|[_EvtChildListScanForChildren_](https://msdn.microsoft.com/library/windows/hardware/ff540838)|1.0|
|[_EvtCleanupCallback_](https://msdn.microsoft.com/library/windows/hardware/ff540840)|1.0|2.0|
|[_EvtCompanionPostD0Exit_](https://msdn.microsoft.com/library/windows/hardware/mt827299)|2.23|
|[_EvtCompanionPostReleaseHardware_](https://msdn.microsoft.com/library/windows/hardware/mt827300)|2.23|
|[_EvtCompanionPreD0Entry_](https://msdn.microsoft.com/library/windows/hardware/mt827301)|2.23|
|[_EvtCompanionPrePrepareHardware_](https://msdn.microsoft.com/library/windows/hardware/mt827302)|2.23|
|[_EvtDestroyCallback_](https://msdn.microsoft.com/library/windows/hardware/ff540841)|1.0|2.0|
|[_EvtDeviceArmWakeFromS0_](https://msdn.microsoft.com/library/windows/hardware/ff540843)|1.0|2.0|
|[_EvtDeviceArmWakeFromSx_](https://msdn.microsoft.com/library/windows/hardware/ff540844)|1.0|2.0|
|[_EvtDeviceArmWakeFromSxWithReason_](https://msdn.microsoft.com/library/windows/hardware/ff540846)|1.7|2.0|
|[_EvtDeviceD0Entry_](https://msdn.microsoft.com/library/windows/hardware/ff540848)|1.0|2.0|
|[_EvtDeviceD0EntryPostInterruptsEnabled_](https://msdn.microsoft.com/library/windows/hardware/ff540853)|1.0|2.0|
|[_EvtDeviceD0Exit_](https://msdn.microsoft.com/library/windows/hardware/ff540855)|1.0|2.0|
|[_EvtDeviceD0ExitPreInterruptsDisabled_](https://msdn.microsoft.com/library/windows/hardware/ff540856)|1.0|2.0|
|[_EvtDeviceDisableWakeAtBus_](https://msdn.microsoft.com/library/windows/hardware/ff540858)|1.0|
|[_EvtDeviceDisarmWakeFromS0_](https://msdn.microsoft.com/library/windows/hardware/ff540860)|1.0|2.0|
|[_EvtDeviceDisarmWakeFromSx_](https://msdn.microsoft.com/library/windows/hardware/ff540862)|1.0|2.0|
|[_EvtDeviceEject_](https://msdn.microsoft.com/library/windows/hardware/ff540863)|1.0|
|[_EvtDeviceEnableWakeAtBus_](https://msdn.microsoft.com/library/windows/hardware/ff540866)|1.0|
|[_EvtDeviceFileCreate_](https://msdn.microsoft.com/library/windows/hardware/ff540868)|1.0|2.0|
|[_EvtDeviceFilterAddResourceRequirements_](https://msdn.microsoft.com/library/windows/hardware/ff540870)|1.0|
|[_EvtDeviceFilterRemoveResourceRequirements_](https://msdn.microsoft.com/library/windows/hardware/ff540872)|1.0|
|[_EvtDevicePnpStateChange_](https://msdn.microsoft.com/library/windows/hardware/ff540874)|1.0|
|[_EvtDevicePowerPolicyStateChange_](https://msdn.microsoft.com/library/windows/hardware/ff540876)|1.0|
|[_EvtDevicePowerStateChange_](https://msdn.microsoft.com/library/windows/hardware/ff540878)|1.0|
|[_EvtDevicePrepareHardware_](https://msdn.microsoft.com/library/windows/hardware/ff540880)|1.0|2.0|
|[_EvtDeviceProcessQueryInterfaceRequest_](https://msdn.microsoft.com/library/windows/hardware/ff540882)|1.0|
|[_EvtDeviceQueryRemove_](https://msdn.microsoft.com/library/windows/hardware/ff540883)|1.0|2.0|
|[_EvtDeviceQueryStop_](https://msdn.microsoft.com/library/windows/hardware/ff540885)|1.0|2.0|
|[_EvtDeviceRelationsQuery_](https://msdn.microsoft.com/library/windows/hardware/ff540886)|1.0|2.0|
|[_EvtDeviceReleaseHardware_](https://msdn.microsoft.com/library/windows/hardware/ff540890)|1.0|2.0|
|[_EvtDeviceRemoveAddedResources_](https://msdn.microsoft.com/library/windows/hardware/ff540892)|1.0|
|[_EvtDeviceReportedMissing_](https://msdn.microsoft.com/library/windows/hardware/hh406360)|1.11|
|[_EvtDeviceResourceRequirementsQuery_](https://msdn.microsoft.com/library/windows/hardware/ff540894)|1.0|
|[_EvtDeviceResourcesQuery_](https://msdn.microsoft.com/library/windows/hardware/ff540895)|1.0|
|[_EvtDeviceSelfManagedIoCleanup_](https://msdn.microsoft.com/library/windows/hardware/ff540898)|1.0|2.0|
|[_EvtDeviceSelfManagedIoFlush_](https://msdn.microsoft.com/library/windows/hardware/ff540901)|1.0|2.0|
|[_EvtDeviceSelfManagedIoInit_](https://msdn.microsoft.com/library/windows/hardware/ff540902)|1.0|2.0|
|[_EvtDeviceSelfManagedIoRestart_](https://msdn.microsoft.com/library/windows/hardware/ff540905)|1.0|2.0|
|[_EvtDeviceSelfManagedIoSuspend_](https://msdn.microsoft.com/library/windows/hardware/ff540907)|1.0|2.0|
|[_EvtDeviceSetLock_](https://msdn.microsoft.com/library/windows/hardware/ff540909)|1.0|
|[_EvtDeviceShutdownNotification_](https://msdn.microsoft.com/library/windows/hardware/ff540911)|1.0|
|[_EvtDeviceSurpriseRemoval_](https://msdn.microsoft.com/library/windows/hardware/ff540913)|1.0|2.0|
|[_EvtDeviceUsageNotification_](https://msdn.microsoft.com/library/windows/hardware/ff540915)|1.0|2.0|
|[_EvtDeviceUsageNotificationEx_](https://msdn.microsoft.com/library/windows/hardware/hh406365)|1.11|2.0|
|[_EvtDeviceWakeFromS0Triggered_](https://msdn.microsoft.com/library/windows/hardware/ff540919)|1.0|2.0|
|[_EvtDeviceWakeFromSxTriggered_](https://msdn.microsoft.com/library/windows/hardware/ff540923)|1.0|2.0|
|[_EvtDeviceWdmIrpDispatch_](https://msdn.microsoft.com/library/windows/hardware/hh406404)|1.11|2.17|
|[_EvtDeviceWdmIrpPreprocess_](https://msdn.microsoft.com/library/windows/hardware/ff540925)|1.0|
|[_EvtDeviceWdmPostPoFxRegisterDevice_](https://msdn.microsoft.com/library/windows/hardware/hh406408)|1.11|
|[_EvtDeviceWdmPrePoFxUnregisterDevice_](https://msdn.microsoft.com/library/windows/hardware/hh406411)|1.11|
|[_EvtDmaEnablerDisable_](https://msdn.microsoft.com/library/windows/hardware/ff540927)|1.0|
|[_EvtDmaEnablerEnable_](https://msdn.microsoft.com/library/windows/hardware/ff540929)|1.0|
|[_EvtDmaEnablerFill_](https://msdn.microsoft.com/library/windows/hardware/ff540932)|1.0|
|[_EvtDmaEnablerFlush_](https://msdn.microsoft.com/library/windows/hardware/ff541655)|1.0|
|[_EvtDmaEnablerSelfManagedIoStart_](https://msdn.microsoft.com/library/windows/hardware/ff541663)|1.0|
|[_EvtDmaEnablerSelfManagedIoStop_](https://msdn.microsoft.com/library/windows/hardware/ff541677)|1.0|
|[_EvtDmaTransactionConfigureDmaChannel_](https://msdn.microsoft.com/library/windows/hardware/hh406414)|1.11|
|[_EvtDmaTransactionDmaTransferComplete_](https://msdn.microsoft.com/library/windows/hardware/hh406418)|1.11|
|[_EvtDpcFunc_](https://msdn.microsoft.com/library/windows/hardware/ff541683)|1.0|
|[_EvtDriverDeviceAdd_](https://msdn.microsoft.com/library/windows/hardware/ff541693)|1.0|2.0|
|[_EvtDriverUnload_](https://msdn.microsoft.com/library/windows/hardware/ff541694)|1.0|2.0|
|[_EvtFileCleanup_](https://msdn.microsoft.com/library/windows/hardware/ff541700)|1.0|2.0|
|[_EvtFileClose_](https://msdn.microsoft.com/library/windows/hardware/ff541702)|1.0|2.0|
|[_EvtInterruptDisable_](https://msdn.microsoft.com/library/windows/hardware/ff541714)|1.0|2.0|
|[_EvtInterruptDpc_](https://msdn.microsoft.com/library/windows/hardware/ff541721)|1.0|2.0|
|[_EvtInterruptEnable_](https://msdn.microsoft.com/library/windows/hardware/ff541730)|1.0|2.0|
|[_EvtInterruptIsr_](https://msdn.microsoft.com/library/windows/hardware/ff541735)|1.0|2.0|
|[_EvtInterruptSynchronize_](https://msdn.microsoft.com/library/windows/hardware/ff541742)|1.0|2.0|
|[_EvtInterruptWorkItem_](https://msdn.microsoft.com/library/windows/hardware/hh406422)|1.11|2.0|
|[_EvtIoAllocateRequestResources_](https://msdn.microsoft.com/library/windows/hardware/ff541747)|1.9|
|[_EvtIoAllocateResourcesForReservedRequest_](https://msdn.microsoft.com/library/windows/hardware/ff541751)|1.9|
|[_EvtIoCanceledOnQueue_](https://msdn.microsoft.com/library/windows/hardware/ff541756)|1.0|2.0|
|[_EvtIoDefault_](https://msdn.microsoft.com/library/windows/hardware/ff541757)|1.0|2.0|
|[_EvtIoDeviceControl_](https://msdn.microsoft.com/library/windows/hardware/ff541758)|1.0|2.0|
|[_EvtIoInCallerContext_](https://msdn.microsoft.com/library/windows/hardware/ff541764)|1.0|
|[_EvtIoInternalDeviceControl_](https://msdn.microsoft.com/library/windows/hardware/ff541768)|1.0|2.0|
|[_EvtIoQueueState_](https://msdn.microsoft.com/library/windows/hardware/ff541771)|1.0|2.0|
|[_EvtIoRead_](https://msdn.microsoft.com/library/windows/hardware/ff541776)|1.0|2.0|
|[_EvtIoResume_](https://msdn.microsoft.com/library/windows/hardware/ff541779)|1.0|2.0|
|[_EvtIoStop_](https://msdn.microsoft.com/library/windows/hardware/ff541788)|1.0|2.0|
|[_EvtIoTargetQueryRemove_](https://msdn.microsoft.com/library/windows/hardware/ff541793)|1.0|2.0|
|[_EvtIoTargetRemoveCanceled_](https://msdn.microsoft.com/library/windows/hardware/ff541800)|1.0|2.0|
|[_EvtIoTargetRemoveComplete_](https://msdn.microsoft.com/library/windows/hardware/ff541806)|1.0|2.0|
|[_EvtIoWdmIrpForForwardProgress_](https://msdn.microsoft.com/library/windows/hardware/ff541808)|1.9|
|[_EvtIoWrite_](https://msdn.microsoft.com/library/windows/hardware/ff541813)|1.0|2.0|
|[_EvtProgramDma_](https://msdn.microsoft.com/library/windows/hardware/ff541816)|1.0|
|[_EvtRequestCancel_](https://msdn.microsoft.com/library/windows/hardware/ff541817)|1.0|2.0|
|[_EvtRequestImpersonate_](https://msdn.microsoft.com/library/windows/hardware/dn265581)|2.0|
|[_EvtReserveDma_](https://msdn.microsoft.com/library/windows/hardware/hh406425)|1.11|
|[_EvtTaskQueueTaskExecuteSync_](https://msdn.microsoft.com/library/windows/hardware/mt827303)|2.23|
|[_EvtTimerFunc_](https://msdn.microsoft.com/library/windows/hardware/ff541823)|1.0|2.0|
|[_EvtUsbTargetPipeReadComplete_](https://msdn.microsoft.com/library/windows/hardware/ff541826)|1.0|2.0|
|[_EvtUsbTargetPipeReadersFailed_](https://msdn.microsoft.com/library/windows/hardware/ff541832)|1.0|2.0|
|[_EvtWmiInstanceExecuteMethod_](https://msdn.microsoft.com/library/windows/hardware/ff541836)|1.0|
|[_EvtWmiInstanceQueryInstance_](https://msdn.microsoft.com/library/windows/hardware/ff541843)|1.0|
|[_EvtWmiInstanceSetInstance_](https://msdn.microsoft.com/library/windows/hardware/ff541847)|1.0|
|[_EvtWmiInstanceSetItem_](https://msdn.microsoft.com/library/windows/hardware/ff541852)|1.0|
|[_EvtWmiProviderFunctionControl_](https://msdn.microsoft.com/library/windows/hardware/ff541855)|1.0|
|[_EvtWorkItem_](https://msdn.microsoft.com/library/windows/hardware/ff541859)|1.0|2.0|
|[**WdfChildListAddOrUpdateChildDescriptionAsPresent**](https://msdn.microsoft.com/library/windows/hardware/ff545591)|1.0|
|[**WdfChildListBeginIteration**](https://msdn.microsoft.com/library/windows/hardware/ff545601)|1.0|
|[**WdfChildListBeginScan**](https://msdn.microsoft.com/library/windows/hardware/ff545608)|1.0|
|[**WdfChildListCreate**](https://msdn.microsoft.com/library/windows/hardware/ff545615)|1.0|
|[**WdfChildListEndIteration**](https://msdn.microsoft.com/library/windows/hardware/ff545618)|1.0|
|[**WdfChildListEndScan**](https://msdn.microsoft.com/library/windows/hardware/ff545626)|1.0|
|[**WdfChildListGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff545636)|1.0|
|[**WdfChildListRequestChildEject**](https://msdn.microsoft.com/library/windows/hardware/ff545641)|1.0|
|[**WdfChildListRetrieveAddressDescription**](https://msdn.microsoft.com/library/windows/hardware/ff545648)|1.0|
|[**WdfChildListRetrieveNextDevice**](https://msdn.microsoft.com/library/windows/hardware/ff545655)|1.0|
|[**WdfChildListRetrievePdo**](https://msdn.microsoft.com/library/windows/hardware/ff545663)|1.0|
|[**WdfChildListUpdateAllChildDescriptionsAsPresent**](https://msdn.microsoft.com/library/windows/hardware/ff545667)|1.0|
|[**WdfChildListUpdateChildDescriptionAsMissing**](https://msdn.microsoft.com/library/windows/hardware/ff545674)|1.0|
|[**WdfCmResourceListAppendDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff545683)|1.0|
|[**WdfCmResourceListGetCount**](https://msdn.microsoft.com/library/windows/hardware/ff545687)|1.0|2.0|
|[**WdfCmResourceListGetDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff545688)|1.0|2.0|
|[**WdfCmResourceListInsertDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff545698)|1.0|
|[**WdfCmResourceListRemove**](https://msdn.microsoft.com/library/windows/hardware/ff545704)|1.0|
|[**WdfCmResourceListRemoveByDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff545717)|1.0|
|[**WdfCollectionAdd**](https://msdn.microsoft.com/library/windows/hardware/ff545732)|1.0|2.0|
|[**WdfCollectionCreate**](https://msdn.microsoft.com/library/windows/hardware/ff545747)|1.0|2.0|
|[**WdfCollectionGetCount**](https://msdn.microsoft.com/library/windows/hardware/ff545759)|1.0|2.0|
|[**WdfCollectionGetFirstItem**](https://msdn.microsoft.com/library/windows/hardware/ff545763)|1.0|2.0|
|[**WdfCollectionGetItem**](https://msdn.microsoft.com/library/windows/hardware/ff545770)|1.0|2.0|
|[**WdfCollectionGetLastItem**](https://msdn.microsoft.com/library/windows/hardware/ff545775)|1.0|2.0|
|[**WdfCollectionRemove**](https://msdn.microsoft.com/library/windows/hardware/ff545784)|1.0|2.0|
|[**WdfCollectionRemoveItem**](https://msdn.microsoft.com/library/windows/hardware/ff545792)|1.0|2.0|
|[**WdfCommonBufferCreate**](https://msdn.microsoft.com/library/windows/hardware/ff545800)|1.0|
|[**WdfCommonBufferCreateWithConfig**](https://msdn.microsoft.com/library/windows/hardware/ff545805)|1.1|
|[**WdfCommonBufferGetAlignedLogicalAddress**](https://msdn.microsoft.com/library/windows/hardware/ff545814)|1.0|
|[**WdfCommonBufferGetAlignedVirtualAddress**](https://msdn.microsoft.com/library/windows/hardware/ff545820)|1.0|
|[**WdfCommonBufferGetLength**](https://msdn.microsoft.com/library/windows/hardware/ff545828)|1.0|
|[**WdfCompanionCreate**](https://msdn.microsoft.com/library/windows/hardware/mt812804)|2.23|
|[**WdfCompanionCreateTaskQueue**](https://msdn.microsoft.com/library/windows/hardware/mt812805)|2.23|
|[**WdfCompanionTargetSendTaskSynchronously**](https://msdn.microsoft.com/library/windows/hardware/mt812806)|1.23|
|[**WdfCompanionTargetWdmGetCompanionProcess**](https://msdn.microsoft.com/library/windows/hardware/mt812807)|1.23|
|[**WdfCompanionWdmGetSecureDeviceHandle**](https://msdn.microsoft.com/library/windows/hardware/mt812808)|2.23|
|[**WdfControlDeviceInitAllocate**](https://msdn.microsoft.com/library/windows/hardware/ff545841)|1.0|
|[**WdfControlDeviceInitSetShutdownNotification**](https://msdn.microsoft.com/library/windows/hardware/ff545847)|1.0|
|[**WdfControlFinishInitializing**](https://msdn.microsoft.com/library/windows/hardware/ff545854)|1.0|
|[**WdfDeviceAddDependentUsageDeviceObject**](https://msdn.microsoft.com/library/windows/hardware/ff545864)|1.0|
|[**WdfDeviceAddQueryInterface**](https://msdn.microsoft.com/library/windows/hardware/ff545870)|1.0|
|[**WdfDeviceAddRemovalRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff545875)|1.0|
|[**WdfDeviceAllocAndQueryInterfaceProperty**](https://msdn.microsoft.com/library/windows/hardware/dn265598)|2.0|
|[**WdfDeviceAllocAndQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff545882)|1.0|2.0|
|[**WdfDeviceAllocAndQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265599)|1.13|2.0|
|[**WdfDeviceAssignInterfaceProperty**](https://msdn.microsoft.com/library/windows/hardware/dn265600)|2.0|
|[**WdfDeviceAssignMofResourceName**](https://msdn.microsoft.com/library/windows/hardware/ff545897)|1.0|
|[**WdfDeviceAssignProperty**](https://msdn.microsoft.com/library/windows/hardware/dn265601)|1.13|2.0|
|[**WdfDeviceAssignS0IdleSettings**](https://msdn.microsoft.com/library/windows/hardware/ff545903)|1.0|2.0|
|[**WdfDeviceAssignSxWakeSettings**](https://msdn.microsoft.com/library/windows/hardware/ff545909)|1.0|2.0|
|[**WdfDeviceClearRemovalRelationsDevices**](https://msdn.microsoft.com/library/windows/hardware/ff545914)|1.0|
|[**WdfDeviceConfigureRequestDispatching**](https://msdn.microsoft.com/library/windows/hardware/ff545920)|1.0|2.0|
|[**WdfDeviceConfigureWdmIrpDispatchCallback**](https://msdn.microsoft.com/library/windows/hardware/hh451093)|1.11|2.17|
|[**WdfDeviceCreate**](https://msdn.microsoft.com/library/windows/hardware/ff545926)|1.0|2.0|
|[**WdfDeviceCreateDeviceInterface**](https://msdn.microsoft.com/library/windows/hardware/ff545935)|1.0|2.0|
|[**WdfDeviceCreateSymbolicLink**](https://msdn.microsoft.com/library/windows/hardware/ff545939)|1.0|2.0|
|[**WdfDeviceEnqueueRequest**](https://msdn.microsoft.com/library/windows/hardware/ff545945)|1.0|
|[**WdfDeviceGetAlignmentRequirement**](https://msdn.microsoft.com/library/windows/hardware/ff545953)|1.0|
|[**WdfDeviceGetCharacteristics**](https://msdn.microsoft.com/library/windows/hardware/ff545960)|1.0|
|[**WdfDeviceGetDefaultQueue**](https://msdn.microsoft.com/library/windows/hardware/ff545965)|1.0|2.0|
|[**WdfDeviceGetDevicePnpState**](https://msdn.microsoft.com/library/windows/hardware/ff545969)|1.0|
|[**WdfDeviceGetDevicePowerPolicyState**](https://msdn.microsoft.com/library/windows/hardware/ff545974)|1.0|
|[**WdfDeviceGetDevicePowerState**](https://msdn.microsoft.com/library/windows/hardware/ff545985)|1.0|
|[**WdfDeviceGetDeviceStackIoType**](https://msdn.microsoft.com/library/windows/hardware/dn265602)|2.0|
|[**WdfDeviceGetDeviceState**](https://msdn.microsoft.com/library/windows/hardware/ff545994)|1.0|2.0|
|[**WdfDeviceGetDriver**](https://msdn.microsoft.com/library/windows/hardware/ff545998)|1.0|2.0|
|[**WdfDeviceGetFileObject**](https://msdn.microsoft.com/library/windows/hardware/ff546007)|1.0|
|[**WdfDeviceGetHardwareRegisterMappedAddress**](https://msdn.microsoft.com/library/windows/hardware/dn265603)|2.0|
|[**WdfDeviceGetIoTarget**](https://msdn.microsoft.com/library/windows/hardware/ff546017)|1.0|2.0|
|[**WdfDeviceGetSystemPowerAction**](https://msdn.microsoft.com/library/windows/hardware/ff546022)|1.9|2.0|
|[**WdfDeviceIndicateWakeStatus**](https://msdn.microsoft.com/library/windows/hardware/ff546025)|1.0|
|[**WdfDeviceInitAssignName**](https://msdn.microsoft.com/library/windows/hardware/ff546029)|1.0|
|[**WdfDeviceInitAssignSDDLString**](https://msdn.microsoft.com/library/windows/hardware/ff546035)|1.0|
|[**WdfDeviceInitAssignWdmIrpPreprocessCallback**](https://msdn.microsoft.com/library/windows/hardware/ff546043)|1.0|
|[**WdfDeviceInitFree**](https://msdn.microsoft.com/library/windows/hardware/ff546050)|1.0|
|[**WdfDeviceInitRegisterPnpStateChangeCallback**](https://msdn.microsoft.com/library/windows/hardware/ff546057)|1.0|
|[**WdfDeviceInitRegisterPowerPolicyStateChangeCallback**](https://msdn.microsoft.com/library/windows/hardware/ff546066)|1.0|
|[**WdfDeviceInitRegisterPowerStateChangeCallback**](https://msdn.microsoft.com/library/windows/hardware/ff546071)|1.0|
|[**WdfDeviceInitSetCharacteristics**](https://msdn.microsoft.com/library/windows/hardware/ff546074)|1.0|
|[**WdfDeviceInitSetDeviceClass**](https://msdn.microsoft.com/library/windows/hardware/ff546084)|1.0|
|[**WdfDeviceInitSetDeviceType**](https://msdn.microsoft.com/library/windows/hardware/ff546090)|1.0|
|[**WdfDeviceInitSetExclusive**](https://msdn.microsoft.com/library/windows/hardware/ff546097)|1.0|
|[**WdfDeviceInitSetFileObjectConfig**](https://msdn.microsoft.com/library/windows/hardware/ff546107)|1.0|2.0|
|[**WdfDeviceInitSetIoInCallerContextCallback**](https://msdn.microsoft.com/library/windows/hardware/ff546119)|1.0|
|[**WdfDeviceInitSetIoType**](https://msdn.microsoft.com/library/windows/hardware/ff546128)|1.0|2.0|
|[**WdfDeviceInitSetIoTypeEx**](https://msdn.microsoft.com/library/windows/hardware/dn265604)|1.13|2.0|
|[**WdfDeviceInitSetPnpPowerEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff546135)|1.0|2.0|
|[**WdfDeviceInitSetPowerInrush**](https://msdn.microsoft.com/library/windows/hardware/ff546142)|1.0|
|[**WdfDeviceInitSetPowerNotPageable**](https://msdn.microsoft.com/library/windows/hardware/ff546147)|1.0|
|[**WdfDeviceInitSetPowerPageable**](https://msdn.microsoft.com/library/windows/hardware/ff546766)|1.0|
|[**WdfDeviceInitSetPowerPolicyEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff546774)|1.0|2.0|
|[**WdfDeviceInitSetPowerPolicyOwnership**](https://msdn.microsoft.com/library/windows/hardware/ff546776)|1.0|2.0|
|[**WdfDeviceInitSetReleaseHardwareOrderOnFailure**](https://msdn.microsoft.com/library/windows/hardware/hh706196)|1.11|2.0|
|[**WdfDeviceInitSetRemoveLockOptions**](https://msdn.microsoft.com/library/windows/hardware/hh451095)|1.11|
|[**WdfDeviceInitSetRequestAttributes**](https://msdn.microsoft.com/library/windows/hardware/ff546786)|1.0|2.0|
|[**WdfDeviceInterfaceDereferenceNoOp**](https://msdn.microsoft.com/library/windows/hardware/ff546790)|1.0|
|[**WdfDeviceInterfaceReferenceNoOp**](https://msdn.microsoft.com/library/windows/hardware/ff546796)|1.0|
|[**WdfDeviceMapIoSpace**](https://msdn.microsoft.com/library/windows/hardware/dn265605)|2.0|
|[**WdfDeviceMiniportCreate**](https://msdn.microsoft.com/library/windows/hardware/ff546802)|1.0|
|[**WdfDeviceOpenDevicemapKey**](https://msdn.microsoft.com/library/windows/hardware/dn932458)|1.15|2.15|
|[**WdfDeviceOpenRegistryKey**](https://msdn.microsoft.com/library/windows/hardware/ff546804)|1.0|2.0|
|[**WdfDevicePostEvent**](https://msdn.microsoft.com/library/windows/hardware/dn265606)|2.0|
|[**WdfDeviceQueryInterfaceProperty**](https://msdn.microsoft.com/library/windows/hardware/dn265607)|2.0|
|[**WdfDeviceQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff546820)|1.0|2.0|
|[**WdfDeviceQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265608)|1.13|2.0|
|[**WdfDeviceReadFromHardware**](https://msdn.microsoft.com/library/windows/hardware/dn265609)|
|[**WdfDeviceRemoveDependentUsageDeviceObject**](https://msdn.microsoft.com/library/windows/hardware/ff546829)|1.9|
|[**WdfDeviceRemoveRemovalRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff546834)|1.0|
|[**WdfDeviceResumeIdle**](https://msdn.microsoft.com/library/windows/hardware/ff546838)|1.0|2.0|
|[**WdfDeviceResumeIdleWithTag**](https://msdn.microsoft.com/library/windows/hardware/dn932459)|1.15|2.15|
|[**WdfDeviceRetrieveDeviceInterfaceString**](https://msdn.microsoft.com/library/windows/hardware/ff546842)|1.0|2.0|
|[**WdfDeviceRetrieveDeviceName**](https://msdn.microsoft.com/library/windows/hardware/ff546853)|1.0|
|[**WdfDeviceSetAlignmentRequirement**](https://msdn.microsoft.com/library/windows/hardware/ff546861)|1.0|
|[**WdfDeviceSetBusInformationForChildren**](https://msdn.microsoft.com/library/windows/hardware/ff546868)|1.0|
|[**WdfDeviceSetCharacteristics**](https://msdn.microsoft.com/library/windows/hardware/ff546872)|1.0|
|[**WdfDeviceSetDeviceInterfaceState**](https://msdn.microsoft.com/library/windows/hardware/ff546878)|1.0|2.0|
|[**WdfDeviceSetDeviceState**](https://msdn.microsoft.com/library/windows/hardware/ff546884)|1.0|2.0|
|[**WdfDeviceSetFailed**](https://msdn.microsoft.com/library/windows/hardware/ff546890)|1.0|2.0|
|[**WdfDeviceSetPnpCapabilities**](https://msdn.microsoft.com/library/windows/hardware/ff546898)|1.0|2.0|
|[**WdfDeviceSetPowerCapabilities**](https://msdn.microsoft.com/library/windows/hardware/ff546901)|1.0|2.0|
|[**WdfDeviceSetSpecialFileSupport**](https://msdn.microsoft.com/library/windows/hardware/ff546903)|1.0|
|[**WdfDeviceSetStaticStopRemove**](https://msdn.microsoft.com/library/windows/hardware/ff546915)|1.0|2.0|
|[**WdfDeviceStopIdle**](https://msdn.microsoft.com/library/windows/hardware/ff546921)|1.0|2.0|
|[**WdfDeviceStopIdleWithTag**](https://msdn.microsoft.com/library/windows/hardware/dn932460)|1.15|2.15|
|[**WdfDeviceUnmapIoSpace**](https://msdn.microsoft.com/library/windows/hardware/dn265610)|2.0|
|[**WdfDeviceWdmAssignPowerFrameworkSettings**](https://msdn.microsoft.com/library/windows/hardware/hh451097)|1.11|
|[**WdfDeviceWdmDispatchIrp**](https://msdn.microsoft.com/library/windows/hardware/hh451100)|1.11|2.17|
|[**WdfDeviceWdmDispatchIrpToIoQueue**](https://msdn.microsoft.com/library/windows/hardware/hh451105)|1.11|2.17|
|[**WdfDeviceWdmDispatchPreprocessedIrp**](https://msdn.microsoft.com/library/windows/hardware/ff546927)|1.0|
|[**WdfDeviceWdmGetAttachedDevice**](https://msdn.microsoft.com/library/windows/hardware/ff546934)|1.0|
|[**WdfDeviceWdmGetDeviceObject**](https://msdn.microsoft.com/library/windows/hardware/ff546942)|1.0|
|[**WdfDeviceWdmGetPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff546946)|1.0|
|[**WdfDeviceWriteToHardware**](https://msdn.microsoft.com/library/windows/hardware/dn265611)|
|[**WdfDevStateIsNP**](https://msdn.microsoft.com/library/windows/hardware/ff546958)|1.0|2.0|
|[**WdfDevStateNormalize**](https://msdn.microsoft.com/library/windows/hardware/ff546966)|1.0|2.0|
|[**WdfDmaEnablerConfigureSystemProfile**](https://msdn.microsoft.com/library/windows/hardware/hh451108)|1.11|
|[**WdfDmaEnablerCreate**](https://msdn.microsoft.com/library/windows/hardware/ff546983)|1.0|
|[**WdfDmaEnablerGetFragmentLength**](https://msdn.microsoft.com/library/windows/hardware/ff546986)|1.1|
|[**WdfDmaEnablerGetMaximumLength**](https://msdn.microsoft.com/library/windows/hardware/ff546994)|1.0|
|[**WdfDmaEnablerGetMaximumScatterGatherElements**](https://msdn.microsoft.com/library/windows/hardware/ff547005)|1.0|
|[**WdfDmaEnablerSetMaximumScatterGatherElements**](https://msdn.microsoft.com/library/windows/hardware/ff547014)|1.0|
|[**WdfDmaEnablerWdmGetDmaAdapter**](https://msdn.microsoft.com/library/windows/hardware/ff547020)|1.5|
|[**WdfDmaTransactionAllocateResources**](https://msdn.microsoft.com/library/windows/hardware/hh451123)|1.11|
|[**WdfDmaTransactionCancel**](https://msdn.microsoft.com/library/windows/hardware/hh451127)|1.11|
|[**WdfDmaTransactionCreate**](https://msdn.microsoft.com/library/windows/hardware/ff547027)|1.0|
|[**WdfDmaTransactionDmaCompleted**](https://msdn.microsoft.com/library/windows/hardware/ff547039)|1.0|
|[**WdfDmaTransactionDmaCompletedFinal**](https://msdn.microsoft.com/library/windows/hardware/ff547049)|1.0|
|[**WdfDmaTransactionDmaCompletedWithLength**](https://msdn.microsoft.com/library/windows/hardware/ff547052)|1.0|
|[**WdfDmaTransactionExecute**](https://msdn.microsoft.com/library/windows/hardware/ff547062)|1.0|
|[**WdfDmaTransactionFreeResources**](https://msdn.microsoft.com/library/windows/hardware/hh451177)|1.11|
|[**WdfDmaTransactionGetBytesTransferred**](https://msdn.microsoft.com/library/windows/hardware/ff547072)|1.0|
|[**WdfDmaTransactionGetCurrentDmaTransferLength**](https://msdn.microsoft.com/library/windows/hardware/ff547081)|1.0|
|[**WdfDmaTransactionGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547085)|1.0|
|[**WdfDmaTransactionGetRequest**](https://msdn.microsoft.com/library/windows/hardware/ff547094)|1.0|
|[**WdfDmaTransactionGetTransferInfo**](https://msdn.microsoft.com/library/windows/hardware/hh451179)|1.11|
|[**WdfDmaTransactionInitialize**](https://msdn.microsoft.com/library/windows/hardware/ff547099)|1.0|
|[**WdfDmaTransactionInitializeUsingOffset**](https://msdn.microsoft.com/library/windows/hardware/hh451182)|1.11|
|[**WdfDmaTransactionInitializeUsingRequest**](https://msdn.microsoft.com/library/windows/hardware/ff547107)|1.0|
|[**WdfDmaTransactionRelease**](https://msdn.microsoft.com/library/windows/hardware/ff547114)|1.0|
|[**WdfDmaTransactionSetChannelConfigurationCallback**](https://msdn.microsoft.com/library/windows/hardware/hh451184)|1.11|
|[**WdfDmaTransactionSetDeviceAddressOffset**](https://msdn.microsoft.com/library/windows/hardware/hh451188)|1.11|
|[**WdfDmaTransactionSetImmediateExecution**](https://msdn.microsoft.com/library/windows/hardware/hh451190)|1.11|
|[**WdfDmaTransactionSetMaximumLength**](https://msdn.microsoft.com/library/windows/hardware/ff547127)|1.0|
|[**WdfDmaTransactionSetSingleTransferRequirement**](https://msdn.microsoft.com/library/windows/hardware/mt734973)|1.19|
|[**WdfDmaTransactionSetTransferCompleteCallback**](https://msdn.microsoft.com/library/windows/hardware/hh439261)|1.11|
|[**WdfDmaTransactionStopSystemTransfer**](https://msdn.microsoft.com/library/windows/hardware/hh439264)|1.11|
|[**WdfDmaTransactionWdmGetTransferContext**](https://msdn.microsoft.com/library/windows/hardware/hh439267)|1.11|
|[**WdfDpcCancel**](https://msdn.microsoft.com/library/windows/hardware/ff547130)|1.0|
|[**WdfDpcCreate**](https://msdn.microsoft.com/library/windows/hardware/ff547140)|1.0|
|[**WdfDpcEnqueue**](https://msdn.microsoft.com/library/windows/hardware/ff547148)|1.0|
|[**WdfDpcGetParentObject**](https://msdn.microsoft.com/library/windows/hardware/ff547157)|1.0|
|[**WdfDpcWdmGetDpc**](https://msdn.microsoft.com/library/windows/hardware/ff547167)|1.0|
|[**WdfDriverCreate**](https://msdn.microsoft.com/library/windows/hardware/ff547175)|1.0|2.0|
|[**WdfDriverGetRegistryPath**](https://msdn.microsoft.com/library/windows/hardware/ff547187)|1.0|2.0|
|[**WdfDriverIsVersionAvailable**](https://msdn.microsoft.com/library/windows/hardware/ff547190)|1.0|2.0|
|[**WdfDriverMiniportUnload**](https://msdn.microsoft.com/library/windows/hardware/ff547193)|1.0|
|[**WdfDriverOpenParametersRegistryKey**](https://msdn.microsoft.com/library/windows/hardware/ff547202)|1.0|2.0|
|[**WdfDriverRegisterTraceInfo**](https://msdn.microsoft.com/library/windows/hardware/ff547206)|
|[**WdfDriverRetrieveVersionString**](https://msdn.microsoft.com/library/windows/hardware/ff547211)|1.0|2.0|
|[**WdfDriverWdmGetDriverObject**](https://msdn.microsoft.com/library/windows/hardware/ff547218)|1.0|
|[**WdfFdoAddStaticChild**](https://msdn.microsoft.com/library/windows/hardware/ff547225)|1.0|
|[**WdfFdoGetDefaultChildList**](https://msdn.microsoft.com/library/windows/hardware/ff547235)|1.0|
|[**WdfFdoInitAllocAndQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547239)|1.0|2.0|
|[**WdfFdoInitAllocAndQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265612)|1.13|2.0|
|[**WdfFdoInitOpenRegistryKey**](https://msdn.microsoft.com/library/windows/hardware/ff547249)|1.0|2.0|
|[**WdfFdoInitQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547254)|1.0|2.0|
|[**WdfFdoInitQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265613)|1.13|2.0|
|[**WdfFdoInitSetDefaultChildListConfig**](https://msdn.microsoft.com/library/windows/hardware/ff547258)|1.0|
|[**WdfFdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff547268)|1.0|
|[**WdfFdoInitSetFilter**](https://msdn.microsoft.com/library/windows/hardware/ff547273)|1.0|2.0|
|[**WdfFdoInitWdmGetPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547281)|1.0|
|[**WdfFdoLockStaticChildListForIteration**](https://msdn.microsoft.com/library/windows/hardware/ff547282)|1.0|
|[**WdfFdoQueryForInterface**](https://msdn.microsoft.com/library/windows/hardware/ff547289)|1.0|
|[**WdfFdoRetrieveNextStaticChild**](https://msdn.microsoft.com/library/windows/hardware/ff547293)|1.0|
|[**WdfFdoUnlockStaticChildListFromIteration**](https://msdn.microsoft.com/library/windows/hardware/ff547297)|1.0|
|[**WdfFileObjectGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547302)|1.0|2.0|
|[**WdfFileObjectGetFileName**](https://msdn.microsoft.com/library/windows/hardware/ff547310)|1.0|2.0|
|[**WdfFileObjectGetFlags**](https://msdn.microsoft.com/library/windows/hardware/ff547316)|1.0|
|[**WdfFileObjectGetInitiatorProcessId**](https://msdn.microsoft.com/library/windows/hardware/dn265614)|1.21|2.0|
|[**WdfFileObjectGetRelatedFileObject**](https://msdn.microsoft.com/library/windows/hardware/dn265615)|2.0|
|[**WdfFileObjectWdmGetFileObject**](https://msdn.microsoft.com/library/windows/hardware/ff547324)|1.0|
|[**WdfGetDriver**](https://msdn.microsoft.com/library/windows/hardware/ff547336)|1.0|2.0|
|[**WdfGetTriageInfo**](https://msdn.microsoft.com/library/windows/hardware/hh706200)|1.11|2.0|
|[**WdfInterruptAcquireLock**](https://msdn.microsoft.com/library/windows/hardware/ff547340)|1.0|2.0|
|[**WdfInterruptCreate**](https://msdn.microsoft.com/library/windows/hardware/ff547345)|1.0|2.0|
|[**WdfInterruptDisable**](https://msdn.microsoft.com/library/windows/hardware/ff547351)|1.0|2.0|
|[**WdfInterruptEnable**](https://msdn.microsoft.com/library/windows/hardware/ff547354)|1.0|2.0|
|[**WdfInterruptGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547358)|1.0|2.0|
|[**WdfInterruptGetInfo**](https://msdn.microsoft.com/library/windows/hardware/ff547367)|1.0|2.0|
|[**WdfInterruptQueueDpcForIsr**](https://msdn.microsoft.com/library/windows/hardware/ff547371)|1.0|2.0|
|[**WdfInterruptQueueWorkItemForIsr**](https://msdn.microsoft.com/library/windows/hardware/hh439270)|1.11|2.0|
|[**WdfInterruptReleaseLock**](https://msdn.microsoft.com/library/windows/hardware/ff547376)|1.0|2.0|
|[**WdfInterruptReportActive**](https://msdn.microsoft.com/library/windows/hardware/hh439273)|1.11|
|[**WdfInterruptReportInactive**](https://msdn.microsoft.com/library/windows/hardware/hh439277)|1.11|
|[**WdfInterruptSetExtendedPolicy**](https://msdn.microsoft.com/library/windows/hardware/ff547381)|1.9|2.0|
|[**WdfInterruptSetPolicy**](https://msdn.microsoft.com/library/windows/hardware/ff547387)|1.0|2.0|
|[**WdfInterruptSynchronize**](https://msdn.microsoft.com/library/windows/hardware/ff547389)|1.0|2.0|
|[**WdfInterruptTryToAcquireLock**](https://msdn.microsoft.com/library/windows/hardware/hh439284)|1.11|2.0|
|[**WdfInterruptWdmGetInterrupt**](https://msdn.microsoft.com/library/windows/hardware/ff547393)|1.0|
|[**WdfIoQueueAssignForwardProgressPolicy**](https://msdn.microsoft.com/library/windows/hardware/ff547395)|1.9|
|[**WdfIoQueueCreate**](https://msdn.microsoft.com/library/windows/hardware/ff547401)|1.0|2.0|
|[**WdfIoQueueDrain**](https://msdn.microsoft.com/library/windows/hardware/ff547406)|1.0|2.0|
|[**WdfIoQueueDrainSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff547412)|1.0|2.0|
|[**WdfIoQueueFindRequest**](https://msdn.microsoft.com/library/windows/hardware/ff547415)|1.0|2.0|
|[**WdfIoQueueGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547421)|1.0|2.0|
|[**WdfIoQueueGetState**](https://msdn.microsoft.com/library/windows/hardware/ff548437)|1.0|2.0|
|[**WdfIoQueuePurge**](https://msdn.microsoft.com/library/windows/hardware/ff548442)|1.0|2.0|
|[**WdfIoQueuePurgeSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548449)|1.0|2.0|
|[**WdfIoQueueReadyNotify**](https://msdn.microsoft.com/library/windows/hardware/ff548452)|1.0|2.0|
|[**WdfIoQueueRetrieveFoundRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548456)|1.0|2.0|
|[**WdfIoQueueRetrieveNextRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548462)|1.0|2.0|
|[**WdfIoQueueRetrieveRequestByFileObject**](https://msdn.microsoft.com/library/windows/hardware/ff548470)|1.0|2.0|
|[**WdfIoQueueStart**](https://msdn.microsoft.com/library/windows/hardware/ff548478)|1.0|2.0|
|[**WdfIoQueueStop**](https://msdn.microsoft.com/library/windows/hardware/ff548482)|1.0|2.0|
|[**WdfIoQueueStopAndPurge**](https://msdn.microsoft.com/library/windows/hardware/hh439289)|1.11|2.0|
|[**WdfIoQueueStopAndPurgeSynchronously**](https://msdn.microsoft.com/library/windows/hardware/hh439293)|1.11|2.0|
|[**WdfIoQueueStopSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548489)|1.0|2.0|
|[**WdfIoResourceListAppendDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff548498)|1.0|
|[**WdfIoResourceListCreate**](https://msdn.microsoft.com/library/windows/hardware/ff548502)|1.0|
|[**WdfIoResourceListGetCount**](https://msdn.microsoft.com/library/windows/hardware/ff548506)|1.0|
|[**WdfIoResourceListGetDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff548510)|1.0|
|[**WdfIoResourceListInsertDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff548513)|1.0|
|[**WdfIoResourceListRemove**](https://msdn.microsoft.com/library/windows/hardware/ff548523)|1.0|
|[**WdfIoResourceListRemoveByDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff548528)|1.0|
|[**WdfIoResourceListUpdateDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff548533)|1.0|
|[**WdfIoResourceRequirementsListAppendIoResList**](https://msdn.microsoft.com/library/windows/hardware/ff548537)|1.0|
|[**WdfIoResourceRequirementsListGetCount**](https://msdn.microsoft.com/library/windows/hardware/ff548545)|1.0|
|[**WdfIoResourceRequirementsListGetIoResList**](https://msdn.microsoft.com/library/windows/hardware/ff548553)|1.0|
|[**WdfIoResourceRequirementsListInsertIoResList**](https://msdn.microsoft.com/library/windows/hardware/ff548560)|1.0|
|[**WdfIoResourceRequirementsListRemove**](https://msdn.microsoft.com/library/windows/hardware/ff548570)|1.0|
|[**WdfIoResourceRequirementsListRemoveByIoResList**](https://msdn.microsoft.com/library/windows/hardware/ff548575)|1.0|
|[**WdfIoResourceRequirementsListSetInterfaceType**](https://msdn.microsoft.com/library/windows/hardware/ff548577)|1.0|
|[**WdfIoResourceRequirementsListSetSlotNumber**](https://msdn.microsoft.com/library/windows/hardware/ff548579)|1.0|
|[**WdfIoTargetAllocAndQueryTargetProperty**](https://msdn.microsoft.com/library/windows/hardware/ff548585)|1.0|
|[**WdfIoTargetClose**](https://msdn.microsoft.com/library/windows/hardware/ff548586)|1.0|2.0|
|[**WdfIoTargetCloseForQueryRemove**](https://msdn.microsoft.com/library/windows/hardware/ff548589)|1.0|2.0|
|[**WdfIoTargetCreate**](https://msdn.microsoft.com/library/windows/hardware/ff548591)|1.0|2.0|
|[**WdfIoTargetFormatRequestForInternalIoctl**](https://msdn.microsoft.com/library/windows/hardware/ff548595)|1.0|
|[**WdfIoTargetFormatRequestForInternalIoctlOthers**](https://msdn.microsoft.com/library/windows/hardware/ff548599)|1.0|
|[**WdfIoTargetFormatRequestForIoctl**](https://msdn.microsoft.com/library/windows/hardware/ff548604)|1.0|2.0|
|[**WdfIoTargetFormatRequestForRead**](https://msdn.microsoft.com/library/windows/hardware/ff548612)|1.0|2.0|
|[**WdfIoTargetFormatRequestForWrite**](https://msdn.microsoft.com/library/windows/hardware/ff548620)|1.0|2.0|
|[**WdfIoTargetGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548625)|1.0|2.0|
|[**WdfIoTargetGetState**](https://msdn.microsoft.com/library/windows/hardware/ff548631)|1.0|2.0|
|[**WdfIoTargetOpen**](https://msdn.microsoft.com/library/windows/hardware/ff548634)|1.0|2.0|
|[**WdfIoTargetPurge**](https://msdn.microsoft.com/library/windows/hardware/hh439338)|1.11|2.0|
|[**WdfIoTargetQueryForInterface**](https://msdn.microsoft.com/library/windows/hardware/ff548640)|1.0|
|[**WdfIoTargetQueryTargetProperty**](https://msdn.microsoft.com/library/windows/hardware/ff548646)|1.0|
|[**WdfIoTargetSendInternalIoctlOthersSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548651)|1.0|
|[**WdfIoTargetSendInternalIoctlSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548656)|1.0|
|[**WdfIoTargetSendIoctlSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548660)|1.0|2.0|
|[**WdfIoTargetSendReadSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548669)|1.0|2.0|
|[**WdfIoTargetSendWriteSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff548672)|1.0|2.0|
|[**WdfIoTargetStart**](https://msdn.microsoft.com/library/windows/hardware/ff548677)|1.0|2.0|
|[**WdfIoTargetStop**](https://msdn.microsoft.com/library/windows/hardware/ff548680)|1.0|2.0|
|[**WdfIoTargetWdmGetTargetDeviceObject**](https://msdn.microsoft.com/library/windows/hardware/ff548682)|1.0|
|[**WdfIoTargetWdmGetTargetFileHandle**](https://msdn.microsoft.com/library/windows/hardware/ff548683)|1.0|2.15|
|[**WdfIoTargetWdmGetTargetFileObject**](https://msdn.microsoft.com/library/windows/hardware/ff548686)|1.0|
|[**WdfIoTargetWdmGetTargetPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548691)|1.0|
|[**WdfLookasideListCreate**](https://msdn.microsoft.com/library/windows/hardware/ff548694)|1.0|
|[**WdfMemoryAssignBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff548697)|1.0|2.0|
|[**WdfMemoryCopyFromBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff548701)|1.0|2.0|
|[**WdfMemoryCopyToBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff548703)|1.0|2.0|
|[**WdfMemoryCreate**](https://msdn.microsoft.com/library/windows/hardware/ff548706)|1.0|2.0|
|[**WdfMemoryCreateFromLookaside**](https://msdn.microsoft.com/library/windows/hardware/ff548709)|1.0|
|[**WdfMemoryCreatePreallocated**](https://msdn.microsoft.com/library/windows/hardware/ff548712)|1.0|2.0|
|[**WdfMemoryGetBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff548715)|1.0|2.0|
|[**WdfObjectAcquireLock**](https://msdn.microsoft.com/library/windows/hardware/ff548721)|1.0|2.0|
|[**WdfObjectAddCustomType**](https://msdn.microsoft.com/library/windows/hardware/hh439344)|1.11|2.0|
|[**WdfObjectAddCustomTypeWithData**](https://msdn.microsoft.com/library/windows/hardware/hh439350)|1.11|2.0|
|[**WdfObjectAllocateContext**](https://msdn.microsoft.com/library/windows/hardware/ff548723)|1.0|2.0|
|[**WdfObjectContextGetObject**](https://msdn.microsoft.com/library/windows/hardware/ff548727)|1.0|2.0|
|[**WdfObjectCreate**](https://msdn.microsoft.com/library/windows/hardware/ff548730)|1.0|2.0|
|[**WdfObjectDelete**](https://msdn.microsoft.com/library/windows/hardware/ff548734)|1.0|2.0|
|[**WdfObjectDereference**](https://msdn.microsoft.com/library/windows/hardware/ff548739)|1.0|2.0|
|[**WdfObjectDereferenceActual**](https://msdn.microsoft.com/library/windows/hardware/ff548743)|1.0|2.0|
|[**WdfObjectDereferenceWithTag**](https://msdn.microsoft.com/library/windows/hardware/ff548746)|1.0|2.0|
|[**WdfObjectGetCustomTypeData**](https://msdn.microsoft.com/library/windows/hardware/hh439356)|1.11|2.0|
|[**WdfObjectGetTypedContext**](https://msdn.microsoft.com/library/windows/hardware/ff548749)|1.0|2.0|
|[**WdfObjectGetTypedContextWorker**](https://msdn.microsoft.com/library/windows/hardware/ff548751)|
|[**WdfObjectIsCustomType**](https://msdn.microsoft.com/library/windows/hardware/hh439362)|1.11|2.0|
|[**WdfObjectQuery**](https://msdn.microsoft.com/library/windows/hardware/ff548752)|
|[**WdfObjectReference**](https://msdn.microsoft.com/library/windows/hardware/ff548758)|1.0|2.0|
|[**WdfObjectReferenceActual**](https://msdn.microsoft.com/library/windows/hardware/ff548760)|1.0|2.0|
|[**WdfObjectReferenceWithTag**](https://msdn.microsoft.com/library/windows/hardware/ff548763)|1.0|2.0|
|[**WdfObjectReleaseLock**](https://msdn.microsoft.com/library/windows/hardware/ff548765)|1.0|2.0|
|[**WdfPdoAddEjectionRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548770)|1.0|
|[**WdfPdoClearEjectionRelationsDevices**](https://msdn.microsoft.com/library/windows/hardware/ff548771)|1.0|
|[**WdfPdoGetParent**](https://msdn.microsoft.com/library/windows/hardware/ff548774)|1.0|
|[**WdfPdoInitAddCompatibleID**](https://msdn.microsoft.com/library/windows/hardware/ff548776)|1.0|
|[**WdfPdoInitAddDeviceText**](https://msdn.microsoft.com/library/windows/hardware/ff548780)|1.0|
|[**WdfPdoInitAddHardwareID**](https://msdn.microsoft.com/library/windows/hardware/ff548784)|1.0|
|[**WdfPdoInitAllocate**](https://msdn.microsoft.com/library/windows/hardware/ff548786)|1.0|
|[**WdfPdoInitAllowForwardingRequestToParent**](https://msdn.microsoft.com/library/windows/hardware/ff548789)|1.9|
|[**WdfPdoInitAssignContainerID**](https://msdn.microsoft.com/library/windows/hardware/ff548792)|1.9|
|[**WdfPdoInitAssignDeviceID**](https://msdn.microsoft.com/library/windows/hardware/ff548797)|1.0|
|[**WdfPdoInitAssignInstanceID**](https://msdn.microsoft.com/library/windows/hardware/ff548799)|1.0|
|[**WdfPdoInitAssignRawDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548802)|1.0|
|[**WdfPdoInitSetDefaultLocale**](https://msdn.microsoft.com/library/windows/hardware/ff548803)|1.0|
|[**WdfPdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff548805)|1.0|
|[**WdfPdoMarkMissing**](https://msdn.microsoft.com/library/windows/hardware/ff548809)|1.0|
|[**WdfPdoRemoveEjectionRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548814)|1.0|
|[**WdfPdoRequestEject**](https://msdn.microsoft.com/library/windows/hardware/ff548817)|1.0|
|[**WdfPdoRetrieveAddressDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548820)|1.0|
|[**WdfPdoRetrieveIdentificationDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548824)|1.0|
|[**WdfPdoUpdateAddressDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548826)|1.0|
|[**WdfPostDeviceInstall**](https://msdn.microsoft.com/library/windows/hardware/ff548829)|1.0|
|[**WdfPostDeviceRemove**](https://msdn.microsoft.com/library/windows/hardware/ff548833)|1.0|
|[**WdfPreDeviceInstall**](https://msdn.microsoft.com/library/windows/hardware/ff548835)|1.0|
|[**WdfPreDeviceInstallEx**](https://msdn.microsoft.com/library/windows/hardware/ff548839)|1.9|
|[**WdfPreDeviceRemove**](https://msdn.microsoft.com/library/windows/hardware/ff548840)|1.0|
|[**WdfRegistryAssignMemory**](https://msdn.microsoft.com/library/windows/hardware/ff549901)|1.0|2.0|
|[**WdfRegistryAssignMultiString**](https://msdn.microsoft.com/library/windows/hardware/ff549903)|1.0|2.0|
|[**WdfRegistryAssignString**](https://msdn.microsoft.com/library/windows/hardware/ff549906)|1.0|2.0|
|[**WdfRegistryAssignULong**](https://msdn.microsoft.com/library/windows/hardware/ff549910)|1.0|2.0|
|[**WdfRegistryAssignUnicodeString**](https://msdn.microsoft.com/library/windows/hardware/ff549912)|1.0|2.0|
|[**WdfRegistryAssignValue**](https://msdn.microsoft.com/library/windows/hardware/ff549913)|1.0|2.0|
|[**WdfRegistryClose**](https://msdn.microsoft.com/library/windows/hardware/ff549914)|1.0|2.0|
|[**WdfRegistryCreateKey**](https://msdn.microsoft.com/library/windows/hardware/ff549917)|1.0|2.0|
|[**WdfRegistryOpenKey**](https://msdn.microsoft.com/library/windows/hardware/ff549919)|1.0|2.0|
|[**WdfRegistryQueryMemory**](https://msdn.microsoft.com/library/windows/hardware/ff549920)|1.0|2.0|
|[**WdfRegistryQueryMultiString**](https://msdn.microsoft.com/library/windows/hardware/ff549921)|1.0|2.0|
|[**WdfRegistryQueryString**](https://msdn.microsoft.com/library/windows/hardware/ff549923)|1.0|2.0|
|[**WdfRegistryQueryULong**](https://msdn.microsoft.com/library/windows/hardware/ff549925)|1.0|2.0|
|[**WdfRegistryQueryUnicodeString**](https://msdn.microsoft.com/library/windows/hardware/ff549927)|1.0|2.0|
|[**WdfRegistryQueryValue**](https://msdn.microsoft.com/library/windows/hardware/ff549928)|1.0|2.0|
|[**WdfRegistryRemoveKey**](https://msdn.microsoft.com/library/windows/hardware/ff549930)|1.0|2.0|
|[**WdfRegistryRemoveValue**](https://msdn.microsoft.com/library/windows/hardware/ff549932)|1.0|2.0|
|[**WdfRegistryWdmGetHandle**](https://msdn.microsoft.com/library/windows/hardware/ff549935)|1.0|2.0|
|[**WdfRequestAllocateTimer**](https://msdn.microsoft.com/library/windows/hardware/ff549938)|1.0|2.0|
|[**WdfRequestCancelSentRequest**](https://msdn.microsoft.com/library/windows/hardware/ff549941)|1.0|2.0|
|[**WdfRequestChangeTarget**](https://msdn.microsoft.com/library/windows/hardware/ff549943)|1.0|2.0|
|[**WdfRequestComplete**](https://msdn.microsoft.com/library/windows/hardware/ff549945)|1.0|2.0|
|[**WdfRequestCompleteWithInformation**](https://msdn.microsoft.com/library/windows/hardware/ff549948)|1.0|2.0|
|[**WdfRequestCompleteWithPriorityBoost**](https://msdn.microsoft.com/library/windows/hardware/ff549949)|1.0|
|[**WdfRequestCreate**](https://msdn.microsoft.com/library/windows/hardware/ff549951)|1.0|2.0|
|[**WdfRequestCreateFromIrp**](https://msdn.microsoft.com/library/windows/hardware/ff549953)|1.0|
|[**WdfRequestFormatRequestUsingCurrentType**](https://msdn.microsoft.com/library/windows/hardware/ff549955)|1.0|2.0|
|[**WdfRequestForwardToIoQueue**](https://msdn.microsoft.com/library/windows/hardware/ff549958)|1.0|2.0|
|[**WdfRequestForwardToParentDeviceIoQueue**](https://msdn.microsoft.com/library/windows/hardware/ff549959)|1.9|
|[**WdfRequestGetCompletionParams**](https://msdn.microsoft.com/library/windows/hardware/ff549961)|1.0|2.0|
|[**WdfRequestGetEffectiveIoType**](https://msdn.microsoft.com/library/windows/hardware/dn265616)|2.0|
|[**WdfRequestGetFileObject**](https://msdn.microsoft.com/library/windows/hardware/ff549963)|1.0|2.0|
|[**WdfRequestGetInformation**](https://msdn.microsoft.com/library/windows/hardware/ff549965)|1.0|2.0|
|[**WdfRequestGetIoQueue**](https://msdn.microsoft.com/library/windows/hardware/ff549968)|1.0|2.0|
|[**WdfRequestGetParameters**](https://msdn.microsoft.com/library/windows/hardware/ff549969)|1.0|2.0|
|[**WdfRequestGetRequestorMode**](https://msdn.microsoft.com/library/windows/hardware/ff549971)|1.0|2.0|
|[**WdfRequestGetRequestorProcessId**](https://msdn.microsoft.com/library/windows/hardware/dn265617)|1.21|2.0|
|[**WdfRequestGetStatus**](https://msdn.microsoft.com/library/windows/hardware/ff549974)|1.0|2.0|
|[**WdfRequestGetUserModeDriverInitiatedIo**](https://msdn.microsoft.com/library/windows/hardware/dn265618)|2.0|
|[**WdfRequestImpersonate**](https://msdn.microsoft.com/library/windows/hardware/dn265619)|2.0|
|[**WdfRequestIsCanceled**](https://msdn.microsoft.com/library/windows/hardware/ff549976)|1.0|2.0|
|[**WdfRequestIsFrom32BitProcess**](https://msdn.microsoft.com/library/windows/hardware/ff549978)|1.0|2.0|
|[**WdfRequestIsFromUserModeDriver**](https://msdn.microsoft.com/library/windows/hardware/dn265620)|2.0|
|[**WdfRequestIsReserved**](https://msdn.microsoft.com/library/windows/hardware/ff549980)|1.9|
|[**WdfRequestMarkCancelable**](https://msdn.microsoft.com/library/windows/hardware/ff549983)|1.0|2.0|
|[**WdfRequestMarkCancelableEx**](https://msdn.microsoft.com/library/windows/hardware/ff549984)|1.9|2.0|
|[**WdfRequestProbeAndLockUserBufferForRead**](https://msdn.microsoft.com/library/windows/hardware/ff549987)|1.0|
|[**WdfRequestProbeAndLockUserBufferForWrite**](https://msdn.microsoft.com/library/windows/hardware/ff549989)|1.0|
|[**WdfRequestRequeue**](https://msdn.microsoft.com/library/windows/hardware/ff550012)|1.0|2.0|
|[**WdfRequestRetrieveActivityId**](https://msdn.microsoft.com/library/windows/hardware/dn265621)|2.0|
|[**WdfRequestRetrieveInputBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff550014)|1.0|2.0|
|[**WdfRequestRetrieveInputMemory**](https://msdn.microsoft.com/library/windows/hardware/ff550015)|1.0|2.0|
|[**WdfRequestRetrieveInputWdmMdl**](https://msdn.microsoft.com/library/windows/hardware/ff550016)|1.0|
|[**WdfRequestRetrieveOutputBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff550018)|1.0|2.0|
|[**WdfRequestRetrieveOutputMemory**](https://msdn.microsoft.com/library/windows/hardware/ff550019)|1.0|2.0|
|[**WdfRequestRetrieveOutputWdmMdl**](https://msdn.microsoft.com/library/windows/hardware/ff550021)|1.0|
|[**WdfRequestRetrieveUnsafeUserInputBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff550022)|1.0|
|[**WdfRequestRetrieveUnsafeUserOutputBuffer**](https://msdn.microsoft.com/library/windows/hardware/ff550024)|1.0|
|[**WdfRequestReuse**](https://msdn.microsoft.com/library/windows/hardware/ff550026)|1.0|2.0|
|[**WdfRequestSend**](https://msdn.microsoft.com/library/windows/hardware/ff550027)|1.0|2.0|
|[**WdfRequestSetActivityId**](https://msdn.microsoft.com/library/windows/hardware/dn265622)|2.0|
|[**WdfRequestSetCompletionRoutine**](https://msdn.microsoft.com/library/windows/hardware/ff550030)|1.0|2.0|
|[**WdfRequestSetInformation**](https://msdn.microsoft.com/library/windows/hardware/ff550032)|1.0|2.0|
|[**WdfRequestSetUserModeDriverInitiatedIo**](https://msdn.microsoft.com/library/windows/hardware/dn265623)|2.0|
|[**WdfRequestStopAcknowledge**](https://msdn.microsoft.com/library/windows/hardware/ff550033)|1.0|2.0|
|[**WdfRequestUnmarkCancelable**](https://msdn.microsoft.com/library/windows/hardware/ff550035)|1.0|2.0|
|[**WdfRequestWdmFormatUsingStackLocation**](https://msdn.microsoft.com/library/windows/hardware/ff550036)|1.0|
|[**WdfRequestWdmGetIrp**](https://msdn.microsoft.com/library/windows/hardware/ff550037)|1.0|
|[**WdfSpinLockAcquire**](https://msdn.microsoft.com/library/windows/hardware/ff550040)|1.0|2.0|
|[**WdfSpinLockCreate**](https://msdn.microsoft.com/library/windows/hardware/ff550042)|1.0|2.0|
|[**WdfSpinLockRelease**](https://msdn.microsoft.com/library/windows/hardware/ff550044)|1.0|2.0|
|[**WdfStringCreate**](https://msdn.microsoft.com/library/windows/hardware/ff550046)|1.0|2.0|
|[**WdfStringGetUnicodeString**](https://msdn.microsoft.com/library/windows/hardware/ff550049)|1.0|2.0|
|[**WdfTimerCreate**](https://msdn.microsoft.com/library/windows/hardware/ff550050)|1.0|2.0|
|[**WdfTimerGetParentObject**](https://msdn.microsoft.com/library/windows/hardware/ff550052)|1.0|2.0|
|[**WdfTimerStart**](https://msdn.microsoft.com/library/windows/hardware/ff550054)|1.0|2.0|
|[**WdfTimerStop**](https://msdn.microsoft.com/library/windows/hardware/ff550056)|1.0|2.0|
|[**WdfUsbInterfaceGetConfiguredPipe**](https://msdn.microsoft.com/library/windows/hardware/ff550057)|1.0|2.0|
|[**WdfUsbInterfaceGetConfiguredSettingIndex**](https://msdn.microsoft.com/library/windows/hardware/ff550059)|1.0|2.0|
|[**WdfUsbInterfaceGetDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff550060)|1.0|2.0|
|[**WdfUsbInterfaceGetEndpointInformation**](https://msdn.microsoft.com/library/windows/hardware/ff550063)|1.0|2.0|
|[**WdfUsbInterfaceGetInterfaceNumber**](https://msdn.microsoft.com/library/windows/hardware/ff550065)|1.0|2.0|
|[**WdfUsbInterfaceGetNumConfiguredPipes**](https://msdn.microsoft.com/library/windows/hardware/ff550066)|1.0|2.0|
|[**WdfUsbInterfaceGetNumEndpoints**](https://msdn.microsoft.com/library/windows/hardware/ff550068)|1.0|2.0|
|[**WdfUsbInterfaceGetNumSettings**](https://msdn.microsoft.com/library/windows/hardware/ff550070)|1.5|2.0|
|[**WdfUsbInterfaceSelectSetting**](https://msdn.microsoft.com/library/windows/hardware/ff550073)|1.0|2.0|
|[**WdfUsbTargetDeviceAllocAndQueryString**](https://msdn.microsoft.com/library/windows/hardware/ff550074)|1.0|2.0|
|[**WdfUsbTargetDeviceCreate**](https://msdn.microsoft.com/library/windows/hardware/ff550077)|1.0|2.0|
|[**WdfUsbTargetDeviceCreateIsochUrb**](https://msdn.microsoft.com/library/windows/hardware/hh439420)|1.11|
|[**WdfUsbTargetDeviceCreateUrb**](https://msdn.microsoft.com/library/windows/hardware/hh439423)|1.11|
|[**WdfUsbTargetDeviceCreateWithParameters**](https://msdn.microsoft.com/library/windows/hardware/hh439428)|1.11|2.0|
|[**WdfUsbTargetDeviceCyclePortSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff550080)|1.0|
|[**WdfUsbTargetDeviceFormatRequestForControlTransfer**](https://msdn.microsoft.com/library/windows/hardware/ff550082)|1.0|2.0|
|[**WdfUsbTargetDeviceFormatRequestForCyclePort**](https://msdn.microsoft.com/library/windows/hardware/ff550084)|1.0|
|[**WdfUsbTargetDeviceFormatRequestForString**](https://msdn.microsoft.com/library/windows/hardware/ff550086)|1.0|2.0|
|[**WdfUsbTargetDeviceFormatRequestForUrb**](https://msdn.microsoft.com/library/windows/hardware/ff550088)|1.0|
|[**WdfUsbTargetDeviceGetDeviceDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff550090)|1.0|2.0|
|[**WdfUsbTargetDeviceGetInterface**](https://msdn.microsoft.com/library/windows/hardware/ff550092)|1.0|2.0|
|[**WdfUsbTargetDeviceGetIoTarget**](https://msdn.microsoft.com/library/windows/hardware/ff550093)|1.0|2.0|
|[**WdfUsbTargetDeviceGetNumInterfaces**](https://msdn.microsoft.com/library/windows/hardware/ff550094)|1.0|2.0|
|[**WdfUsbTargetDeviceIsConnectedSynchronous**](https://msdn.microsoft.com/library/windows/hardware/ff550095)|1.0|
|[**WdfUsbTargetDeviceQueryString**](https://msdn.microsoft.com/library/windows/hardware/ff550096)|1.0|2.0|
|[**WdfUsbTargetDeviceQueryUsbCapability**](https://msdn.microsoft.com/library/windows/hardware/hh439434)|1.11|2.0|
|[**WdfUsbTargetDeviceResetPortSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff550097)|1.0|2.0|
|[**WdfUsbTargetDeviceRetrieveConfigDescriptor**](https://msdn.microsoft.com/library/windows/hardware/ff550098)|1.0|2.0|
|[**WdfUsbTargetDeviceRetrieveCurrentFrameNumber**](https://msdn.microsoft.com/library/windows/hardware/ff550099)|1.0|
|[**WdfUsbTargetDeviceRetrieveInformation**](https://msdn.microsoft.com/library/windows/hardware/ff550100)|1.0|2.0|
|[**WdfUsbTargetDeviceSelectConfig**](https://msdn.microsoft.com/library/windows/hardware/ff550101)|1.0|2.0|
|[**WdfUsbTargetDeviceSelectConfigType**](https://msdn.microsoft.com/library/windows/hardware/ff550102)|1.0|2.0|
|[**WdfUsbTargetDeviceSelectSettingType**](https://msdn.microsoft.com/library/windows/hardware/ff550103)|1.0|2.0|
|[**WdfUsbTargetDeviceSendControlTransferSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff550104)|1.0|2.0|
|[**WdfUsbTargetDeviceSendUrbSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff550105)|1.0|
|[**WdfUsbTargetDeviceWdmGetConfigurationHandle**](https://msdn.microsoft.com/library/windows/hardware/ff551127)|1.0|
|[**WdfUsbTargetPipeAbortSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff551129)|1.0|2.0|
|[**WdfUsbTargetPipeConfigContinuousReader**](https://msdn.microsoft.com/library/windows/hardware/ff551130)|1.0|2.0|
|[**WdfUsbTargetPipeFormatRequestForAbort**](https://msdn.microsoft.com/library/windows/hardware/ff551132)|1.0|2.0|
|[**WdfUsbTargetPipeFormatRequestForRead**](https://msdn.microsoft.com/library/windows/hardware/ff551136)|1.0|2.0|
|[**WdfUsbTargetPipeFormatRequestForReset**](https://msdn.microsoft.com/library/windows/hardware/ff551138)|1.0|2.0|
|[**WdfUsbTargetPipeFormatRequestForUrb**](https://msdn.microsoft.com/library/windows/hardware/ff551139)|1.0|
|[**WdfUsbTargetPipeFormatRequestForWrite**](https://msdn.microsoft.com/library/windows/hardware/ff551141)|1.0|2.0|
|[**WdfUsbTargetPipeGetInformation**](https://msdn.microsoft.com/library/windows/hardware/ff551142)|1.0|2.0|
|[**WdfUsbTargetPipeGetIoTarget**](https://msdn.microsoft.com/library/windows/hardware/ff551146)|1.0|2.0|
|[**WdfUsbTargetPipeGetType**](https://msdn.microsoft.com/library/windows/hardware/ff551148)|1.0|2.0|
|[**WdfUsbTargetPipeIsInEndpoint**](https://msdn.microsoft.com/library/windows/hardware/ff551151)|1.0|2.0|
|[**WdfUsbTargetPipeIsOutEndpoint**](https://msdn.microsoft.com/library/windows/hardware/ff551153)|1.0|2.0|
|[**WdfUsbTargetPipeReadSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff551155)|1.0|2.0|
|[**WdfUsbTargetPipeResetSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff551156)|1.0|2.0|
|[**WdfUsbTargetPipeSendUrbSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff551158)|1.0|
|[**WdfUsbTargetPipeSetNoMaximumPacketSizeCheck**](https://msdn.microsoft.com/library/windows/hardware/ff551160)|1.0|2.0|
|[**WdfUsbTargetPipeWdmGetPipeHandle**](https://msdn.microsoft.com/library/windows/hardware/ff551162)|1.0|
|[**WdfUsbTargetPipeWriteSynchronously**](https://msdn.microsoft.com/library/windows/hardware/ff551163)|1.0|2.0|
|[**WdfVerifierDbgBreakPoint**](https://msdn.microsoft.com/library/windows/hardware/ff551164)|1.0|2.0|
|[**WdfVerifierKeBugCheck**](https://msdn.microsoft.com/library/windows/hardware/ff551166)|1.0|2.0|
|[**WdfWaitLockAcquire**](https://msdn.microsoft.com/library/windows/hardware/ff551168)|1.0|2.0|
|[**WdfWaitLockCreate**](https://msdn.microsoft.com/library/windows/hardware/ff551171)|1.0|2.0|
|[**WdfWaitLockRelease**](https://msdn.microsoft.com/library/windows/hardware/ff551173)|1.0|2.0|
|[**WdfWdmDeviceGetWdfDeviceHandle**](https://msdn.microsoft.com/library/windows/hardware/ff551175)|1.0|
|[**WdfWdmDriverGetWdfDriverHandle**](https://msdn.microsoft.com/library/windows/hardware/ff551176)|1.0|
|[**WdfWmiInstanceCreate**](https://msdn.microsoft.com/library/windows/hardware/ff551178)|1.0|
|[**WdfWmiInstanceDeregister**](https://msdn.microsoft.com/library/windows/hardware/ff551179)|1.0|
|[**WdfWmiInstanceFireEvent**](https://msdn.microsoft.com/library/windows/hardware/ff551182)|1.0|
|[**WdfWmiInstanceGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff551184)|1.0|
|[**WdfWmiInstanceGetProvider**](https://msdn.microsoft.com/library/windows/hardware/ff551187)|1.0|
|[**WdfWmiInstanceRegister**](https://msdn.microsoft.com/library/windows/hardware/ff551190)|1.0|
|[**WdfWmiProviderCreate**](https://msdn.microsoft.com/library/windows/hardware/ff551193)|1.0|
|[**WdfWmiProviderGetDevice**](https://msdn.microsoft.com/library/windows/hardware/ff551195)|1.0|
|[**WdfWmiProviderGetTracingHandle**](https://msdn.microsoft.com/library/windows/hardware/ff551198)|1.0|
|[**WdfWmiProviderIsEnabled**](https://msdn.microsoft.com/library/windows/hardware/ff551200)|1.0|
|[**WdfWorkItemCreate**](https://msdn.microsoft.com/library/windows/hardware/ff551201)|1.0|2.0|
|[**WdfWorkItemEnqueue**](https://msdn.microsoft.com/library/windows/hardware/ff551203)|1.0|2.0|
|[**WdfWorkItemFlush**](https://msdn.microsoft.com/library/windows/hardware/ff551204)|1.0|2.0|
|[**WdfWorkItemGetParentObject**](https://msdn.microsoft.com/library/windows/hardware/ff551207)|1.0|2.0|

