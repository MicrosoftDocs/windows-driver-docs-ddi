---
UID: TP:wdf
ms.assetid: cf4c7959-f8f4-3342-82e9-ced7b9f1b959
ms.author: windowsdriverdev
ms.date: 04/06/18
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

For a list of framework objects and mode availability, see Summary of Framework Objects.

<table>
<tr>
<th>Name</th>
<th>Minimum KMDF Version</th>
<th>Minimum UMDF Version</th>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistaddressdescriptioncleanup"><i>EvtChildListAddressDescriptionCleanup</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistaddressdescriptioncopy"><i>EvtChildListAddressDescriptionCopy</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistaddressdescriptionduplicate"><i>EvtChildListAddressDescriptionDuplicate</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistcreatedevice"><i>EvtChildListCreateDevice</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistdevicereenumerated"><i>EvtChildListDeviceReenumerated</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistidentificationdescriptioncleanup"><i>EvtChildListIdentificationDescriptionCleanup</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistidentificationdescriptioncompare"><i>EvtChildListIdentificationDescriptionCompare</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistidentificationdescriptioncopy"><i>EvtChildListIdentificationDescriptionCopy</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistidentificationdescriptionduplicate"><i>EvtChildListIdentificationDescriptionDuplicate</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtchildlistscanforchildren"><i>EvtChildListScanForChildren</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtcleanupcallback"><i>EvtCleanupCallback</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evt_wdf_companion_post_d0_exit"><i>EvtCompanionPostD0Exit</i></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evt_wdf_companion_post_release_hardware"><i>EvtCompanionPostReleaseHardware</i></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evt_wdf_companion_pre_d0_entry"><i>EvtCompanionPreD0Entry</i></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evt_wdf_companion_pre_prepare_hardware"><i>EvtCompanionPrePrepareHardware</i></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdestroycallback"><i>EvtDestroyCallback</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicearmwakefroms0"><i>EvtDeviceArmWakeFromS0</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicearmwakefromsx"><i>EvtDeviceArmWakeFromSx</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicearmwakefromsxwithreason"><i>EvtDeviceArmWakeFromSxWithReason</i></mshelp:link>
</td>
<td>1.7</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviced0entry"><i>EvtDeviceD0Entry</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviced0entrypostinterruptsenabled"><i>EvtDeviceD0EntryPostInterruptsEnabled</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviced0exit"><i>EvtDeviceD0Exit</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviced0exitpreinterruptsdisabled"><i>EvtDeviceD0ExitPreInterruptsDisabled</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicedisablewakeatbus"><i>EvtDeviceDisableWakeAtBus</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicedisarmwakefroms0"><i>EvtDeviceDisarmWakeFromS0</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicedisarmwakefromsx"><i>EvtDeviceDisarmWakeFromSx</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceeject"><i>EvtDeviceEject</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceenablewakeatbus"><i>EvtDeviceEnableWakeAtBus</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicefilecreate"><i>EvtDeviceFileCreate</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicefilteraddresourcerequirements"><i>EvtDeviceFilterAddResourceRequirements</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicefilterremoveresourcerequirements"><i>EvtDeviceFilterRemoveResourceRequirements</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicepnpstatechange"><i>EvtDevicePnpStateChange</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicepowerpolicystatechange"><i>EvtDevicePowerPolicyStateChange</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicepowerstatechange"><i>EvtDevicePowerStateChange</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicepreparehardware"><i>EvtDevicePrepareHardware</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceprocessqueryinterfacerequest"><i>EvtDeviceProcessQueryInterfaceRequest</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicequeryremove"><i>EvtDeviceQueryRemove</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicequerystop"><i>EvtDeviceQueryStop</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicerelationsquery"><i>EvtDeviceRelationsQuery</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicereleasehardware"><i>EvtDeviceReleaseHardware</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceremoveaddedresources"><i>EvtDeviceRemoveAddedResources</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicereportedmissing"><i>EvtDeviceReportedMissing</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceresourcerequirementsquery"><i>EvtDeviceResourceRequirementsQuery</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceresourcesquery"><i>EvtDeviceResourcesQuery</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceselfmanagediocleanup"><i>EvtDeviceSelfManagedIoCleanup</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceselfmanagedioflush"><i>EvtDeviceSelfManagedIoFlush</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceselfmanagedioinit"><i>EvtDeviceSelfManagedIoInit</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceselfmanagediorestart"><i>EvtDeviceSelfManagedIoRestart</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceselfmanagediosuspend"><i>EvtDeviceSelfManagedIoSuspend</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicesetlock"><i>EvtDeviceSetLock</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceshutdownnotification"><i>EvtDeviceShutdownNotification</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicesurpriseremoval"><i>EvtDeviceSurpriseRemoval</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceusagenotification"><i>EvtDeviceUsageNotification</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdeviceusagenotificationex"><i>EvtDeviceUsageNotificationEx</i></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewakefroms0triggered"><i>EvtDeviceWakeFromS0Triggered</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewakefromsxtriggered"><i>EvtDeviceWakeFromSxTriggered</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewdmirpdispatch"><i>EvtDeviceWdmIrpDispatch</i></mshelp:link>
</td>
<td>1.11</td>
<td>2.17</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewdmirppreprocess"><i>EvtDeviceWdmIrpPreprocess</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewdmpostpofxregisterdevice"><i>EvtDeviceWdmPostPoFxRegisterDevice</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdevicewdmprepofxunregisterdevice"><i>EvtDeviceWdmPrePoFxUnregisterDevice</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerdisable"><i>EvtDmaEnablerDisable</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerenable"><i>EvtDmaEnablerEnable</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerfill"><i>EvtDmaEnablerFill</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerflush"><i>EvtDmaEnablerFlush</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerselfmanagediostart"><i>EvtDmaEnablerSelfManagedIoStart</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmaenablerselfmanagediostop"><i>EvtDmaEnablerSelfManagedIoStop</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmatransactionconfiguredmachannel"><i>EvtDmaTransactionConfigureDmaChannel</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdmatransactiondmatransfercomplete"><i>EvtDmaTransactionDmaTransferComplete</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdpcfunc"><i>EvtDpcFunc</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdriverdeviceadd"><i>EvtDriverDeviceAdd</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtdriverunload"><i>EvtDriverUnload</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtfilecleanup"><i>EvtFileCleanup</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtfileclose"><i>EvtFileClose</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptdisable"><i>EvtInterruptDisable</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptdpc"><i>EvtInterruptDpc</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptenable"><i>EvtInterruptEnable</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptisr"><i>EvtInterruptIsr</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptsynchronize"><i>EvtInterruptSynchronize</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtinterruptworkitem"><i>EvtInterruptWorkItem</i></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioallocaterequestresources"><i>EvtIoAllocateRequestResources</i></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioallocateresourcesforreservedrequest"><i>EvtIoAllocateResourcesForReservedRequest</i></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiocanceledonqueue"><i>EvtIoCanceledOnQueue</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiodefault"><i>EvtIoDefault</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiodevicecontrol"><i>EvtIoDeviceControl</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioincallercontext"><i>EvtIoInCallerContext</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiointernaldevicecontrol"><i>EvtIoInternalDeviceControl</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioqueuestate"><i>EvtIoQueueState</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioread"><i>EvtIoRead</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtioresume"><i>EvtIoResume</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiostop"><i>EvtIoStop</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiotargetqueryremove"><i>EvtIoTargetQueryRemove</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiotargetremovecanceled"><i>EvtIoTargetRemoveCanceled</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiotargetremovecomplete"><i>EvtIoTargetRemoveComplete</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiowdmirpforforwardprogress"><i>EvtIoWdmIrpForForwardProgress</i></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtiowrite"><i>EvtIoWrite</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtprogramdma"><i>EvtProgramDma</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtrequestcancel"><i>EvtRequestCancel</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtrequestimpersonate"><i>EvtRequestImpersonate</i></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtreservedma"><i>EvtReserveDma</i></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evt_wdf_task_queue_task_execute_sync"><i>EvtTaskQueueTaskExecuteSync</i></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evttimerfunc"><i>EvtTimerFunc</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtusbtargetpipereadcomplete"><i>EvtUsbTargetPipeReadComplete</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtusbtargetpipereadersfailed"><i>EvtUsbTargetPipeReadersFailed</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtwmiinstanceexecutemethod"><i>EvtWmiInstanceExecuteMethod</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtwmiinstancequeryinstance"><i>EvtWmiInstanceQueryInstance</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtwmiinstancesetinstance"><i>EvtWmiInstanceSetInstance</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtwmiinstancesetitem"><i>EvtWmiInstanceSetItem</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtwmiproviderfunctioncontrol"><i>EvtWmiProviderFunctionControl</i></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.evtworkitem"><i>EvtWorkItem</i></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistaddorupdatechilddescriptionaspresent"><b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistbeginiteration"><b>WdfChildListBeginIteration</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistbeginscan"><b>WdfChildListBeginScan</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistcreate"><b>WdfChildListCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistenditeration"><b>WdfChildListEndIteration</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistendscan"><b>WdfChildListEndScan</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistgetdevice"><b>WdfChildListGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistrequestchildeject"><b>WdfChildListRequestChildEject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistretrieveaddressdescription"><b>WdfChildListRetrieveAddressDescription</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistretrievenextdevice"><b>WdfChildListRetrieveNextDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistretrievepdo"><b>WdfChildListRetrievePdo</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistupdateallchilddescriptionsaspresent"><b>WdfChildListUpdateAllChildDescriptionsAsPresent</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfchildlistupdatechilddescriptionasmissing"><b>WdfChildListUpdateChildDescriptionAsMissing</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistappenddescriptor"><b>WdfCmResourceListAppendDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistgetcount"><b>WdfCmResourceListGetCount</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistgetdescriptor"><b>WdfCmResourceListGetDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistinsertdescriptor"><b>WdfCmResourceListInsertDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistremove"><b>WdfCmResourceListRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcmresourcelistremovebydescriptor"><b>WdfCmResourceListRemoveByDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectionadd"><b>WdfCollectionAdd</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectioncreate"><b>WdfCollectionCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectiongetcount"><b>WdfCollectionGetCount</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectiongetfirstitem"><b>WdfCollectionGetFirstItem</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectiongetitem"><b>WdfCollectionGetItem</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectiongetlastitem"><b>WdfCollectionGetLastItem</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectionremove"><b>WdfCollectionRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcollectionremoveitem"><b>WdfCollectionRemoveItem</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcommonbuffercreate"><b>WdfCommonBufferCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcommonbuffercreatewithconfig"><b>WdfCommonBufferCreateWithConfig</b></mshelp:link>
</td>
<td>1.1</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcommonbuffergetalignedlogicaladdress"><b>WdfCommonBufferGetAlignedLogicalAddress</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcommonbuffergetalignedvirtualaddress"><b>WdfCommonBufferGetAlignedVirtualAddress</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcommonbuffergetlength"><b>WdfCommonBufferGetLength</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcompanioncreate"><b>WdfCompanionCreate</b></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcompanioncreatetaskqueue"><b>WdfCompanionCreateTaskQueue</b></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcompaniontargetsendtasksynchronously"><b>WdfCompanionTargetSendTaskSynchronously</b></mshelp:link>
</td>
<td>1.23</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcompaniontargetwdmgetcompanionprocess"><b>WdfCompanionTargetWdmGetCompanionProcess</b></mshelp:link>
</td>
<td>1.23</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcompanionwdmgetsecuredevicehandle"><b>WdfCompanionWdmGetSecureDeviceHandle</b></mshelp:link>
</td>
<td></td>
<td>2.23</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcontroldeviceinitallocate"><b>WdfControlDeviceInitAllocate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcontroldeviceinitsetshutdownnotification"><b>WdfControlDeviceInitSetShutdownNotification</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfcontrolfinishinitializing"><b>WdfControlFinishInitializing</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceadddependentusagedeviceobject"><b>WdfDeviceAddDependentUsageDeviceObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceaddqueryinterface"><b>WdfDeviceAddQueryInterface</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceaddremovalrelationsphysicaldevice"><b>WdfDeviceAddRemovalRelationsPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceallocandqueryinterfaceproperty"><b>WdfDeviceAllocAndQueryInterfaceProperty</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceallocandqueryproperty"><b>WdfDeviceAllocAndQueryProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceallocandquerypropertyex"><b>WdfDeviceAllocAndQueryPropertyEx</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceassigninterfaceproperty"><b>WdfDeviceAssignInterfaceProperty</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceassignmofresourcename"><b>WdfDeviceAssignMofResourceName</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceassignproperty"><b>WdfDeviceAssignProperty</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceassigns0idlesettings"><b>WdfDeviceAssignS0IdleSettings</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceassignsxwakesettings"><b>WdfDeviceAssignSxWakeSettings</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceclearremovalrelationsdevices"><b>WdfDeviceClearRemovalRelationsDevices</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceconfigurerequestdispatching"><b>WdfDeviceConfigureRequestDispatching</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceconfigurewdmirpdispatchcallback"><b>WdfDeviceConfigureWdmIrpDispatchCallback</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.17</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicecreate"><b>WdfDeviceCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicecreatedeviceinterface"><b>WdfDeviceCreateDeviceInterface</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicecreatesymboliclink"><b>WdfDeviceCreateSymbolicLink</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceenqueuerequest"><b>WdfDeviceEnqueueRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetalignmentrequirement"><b>WdfDeviceGetAlignmentRequirement</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetcharacteristics"><b>WdfDeviceGetCharacteristics</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdefaultqueue"><b>WdfDeviceGetDefaultQueue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdevicepnpstate"><b>WdfDeviceGetDevicePnpState</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdevicepowerpolicystate"><b>WdfDeviceGetDevicePowerPolicyState</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdevicepowerstate"><b>WdfDeviceGetDevicePowerState</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdevicestackiotype"><b>WdfDeviceGetDeviceStackIoType</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdevicestate"><b>WdfDeviceGetDeviceState</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetdriver"><b>WdfDeviceGetDriver</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetfileobject"><b>WdfDeviceGetFileObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegethardwareregistermappedaddress"><b>WdfDeviceGetHardwareRegisterMappedAddress</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetiotarget"><b>WdfDeviceGetIoTarget</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicegetsystempoweraction"><b>WdfDeviceGetSystemPowerAction</b></mshelp:link>
</td>
<td>1.9</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceindicatewakestatus"><b>WdfDeviceIndicateWakeStatus</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitassignname"><b>WdfDeviceInitAssignName</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitassignsddlstring"><b>WdfDeviceInitAssignSDDLString</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitassignwdmirppreprocesscallback"><b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitfree"><b>WdfDeviceInitFree</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitregisterpnpstatechangecallback"><b>WdfDeviceInitRegisterPnpStateChangeCallback</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitregisterpowerpolicystatechangecallback"><b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitregisterpowerstatechangecallback"><b>WdfDeviceInitRegisterPowerStateChangeCallback</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetcharacteristics"><b>WdfDeviceInitSetCharacteristics</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetdeviceclass"><b>WdfDeviceInitSetDeviceClass</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetdevicetype"><b>WdfDeviceInitSetDeviceType</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetexclusive"><b>WdfDeviceInitSetExclusive</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetfileobjectconfig"><b>WdfDeviceInitSetFileObjectConfig</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetioincallercontextcallback"><b>WdfDeviceInitSetIoInCallerContextCallback</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetiotype"><b>WdfDeviceInitSetIoType</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetiotypeex"><b>WdfDeviceInitSetIoTypeEx</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpnppowereventcallbacks"><b>WdfDeviceInitSetPnpPowerEventCallbacks</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpowerinrush"><b>WdfDeviceInitSetPowerInrush</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpowernotpageable"><b>WdfDeviceInitSetPowerNotPageable</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpowerpageable"><b>WdfDeviceInitSetPowerPageable</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpowerpolicyeventcallbacks"><b>WdfDeviceInitSetPowerPolicyEventCallbacks</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetpowerpolicyownership"><b>WdfDeviceInitSetPowerPolicyOwnership</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetreleasehardwareorderonfailure"><b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetremovelockoptions"><b>WdfDeviceInitSetRemoveLockOptions</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinitsetrequestattributes"><b>WdfDeviceInitSetRequestAttributes</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinterfacedereferencenoop"><b>WdfDeviceInterfaceDereferenceNoOp</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceinterfacereferencenoop"><b>WdfDeviceInterfaceReferenceNoOp</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicemapiospace"><b>WdfDeviceMapIoSpace</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceminiportcreate"><b>WdfDeviceMiniportCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceopendevicemapkey"><b>WdfDeviceOpenDevicemapKey</b></mshelp:link>
</td>
<td>1.15</td>
<td>2.15</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceopenregistrykey"><b>WdfDeviceOpenRegistryKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicepostevent"><b>WdfDevicePostEvent</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicequeryinterfaceproperty"><b>WdfDeviceQueryInterfaceProperty</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicequeryproperty"><b>WdfDeviceQueryProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicequerypropertyex"><b>WdfDeviceQueryPropertyEx</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicereadfromhardware"><b>WdfDeviceReadFromHardware</b></mshelp:link>
</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceremovedependentusagedeviceobject"><b>WdfDeviceRemoveDependentUsageDeviceObject</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceremoveremovalrelationsphysicaldevice"><b>WdfDeviceRemoveRemovalRelationsPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceresumeidle"><b>WdfDeviceResumeIdle</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceresumeidlewithtag"><b>WdfDeviceResumeIdleWithTag</b></mshelp:link>
</td>
<td>1.15</td>
<td>2.15</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceretrievedeviceinterfacestring"><b>WdfDeviceRetrieveDeviceInterfaceString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceretrievedevicename"><b>WdfDeviceRetrieveDeviceName</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetalignmentrequirement"><b>WdfDeviceSetAlignmentRequirement</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetbusinformationforchildren"><b>WdfDeviceSetBusInformationForChildren</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetcharacteristics"><b>WdfDeviceSetCharacteristics</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetdeviceinterfacestate"><b>WdfDeviceSetDeviceInterfaceState</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetdevicestate"><b>WdfDeviceSetDeviceState</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetfailed"><b>WdfDeviceSetFailed</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetpnpcapabilities"><b>WdfDeviceSetPnpCapabilities</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetpowercapabilities"><b>WdfDeviceSetPowerCapabilities</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetspecialfilesupport"><b>WdfDeviceSetSpecialFileSupport</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicesetstaticstopremove"><b>WdfDeviceSetStaticStopRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicestopidle"><b>WdfDeviceStopIdle</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicestopidlewithtag"><b>WdfDeviceStopIdleWithTag</b></mshelp:link>
</td>
<td>1.15</td>
<td>2.15</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdeviceunmapiospace"><b>WdfDeviceUnmapIoSpace</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmassignpowerframeworksettings"><b>WdfDeviceWdmAssignPowerFrameworkSettings</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmdispatchirp"><b>WdfDeviceWdmDispatchIrp</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.17</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmdispatchirptoioqueue"><b>WdfDeviceWdmDispatchIrpToIoQueue</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.17</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmdispatchpreprocessedirp"><b>WdfDeviceWdmDispatchPreprocessedIrp</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmgetattacheddevice"><b>WdfDeviceWdmGetAttachedDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmgetdeviceobject"><b>WdfDeviceWdmGetDeviceObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewdmgetphysicaldevice"><b>WdfDeviceWdmGetPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevicewritetohardware"><b>WdfDeviceWriteToHardware</b></mshelp:link>
</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevstateisnp"><b>WdfDevStateIsNP</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdevstatenormalize"><b>WdfDevStateNormalize</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablerconfiguresystemprofile"><b>WdfDmaEnablerConfigureSystemProfile</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablercreate"><b>WdfDmaEnablerCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablergetfragmentlength"><b>WdfDmaEnablerGetFragmentLength</b></mshelp:link>
</td>
<td>1.1</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablergetmaximumlength"><b>WdfDmaEnablerGetMaximumLength</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablergetmaximumscattergatherelements"><b>WdfDmaEnablerGetMaximumScatterGatherElements</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablersetmaximumscattergatherelements"><b>WdfDmaEnablerSetMaximumScatterGatherElements</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmaenablerwdmgetdmaadapter"><b>WdfDmaEnablerWdmGetDmaAdapter</b></mshelp:link>
</td>
<td>1.5</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionallocateresources"><b>WdfDmaTransactionAllocateResources</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactioncancel"><b>WdfDmaTransactionCancel</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactioncreate"><b>WdfDmaTransactionCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiondmacompleted"><b>WdfDmaTransactionDmaCompleted</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiondmacompletedfinal"><b>WdfDmaTransactionDmaCompletedFinal</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiondmacompletedwithlength"><b>WdfDmaTransactionDmaCompletedWithLength</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionexecute"><b>WdfDmaTransactionExecute</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionfreeresources"><b>WdfDmaTransactionFreeResources</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiongetbytestransferred"><b>WdfDmaTransactionGetBytesTransferred</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiongetcurrentdmatransferlength"><b>WdfDmaTransactionGetCurrentDmaTransferLength</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiongetdevice"><b>WdfDmaTransactionGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiongetrequest"><b>WdfDmaTransactionGetRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactiongettransferinfo"><b>WdfDmaTransactionGetTransferInfo</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactioninitialize"><b>WdfDmaTransactionInitialize</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactioninitializeusingoffset"><b>WdfDmaTransactionInitializeUsingOffset</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactioninitializeusingrequest"><b>WdfDmaTransactionInitializeUsingRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionrelease"><b>WdfDmaTransactionRelease</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsetchannelconfigurationcallback"><b>WdfDmaTransactionSetChannelConfigurationCallback</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsetdeviceaddressoffset"><b>WdfDmaTransactionSetDeviceAddressOffset</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsetimmediateexecution"><b>WdfDmaTransactionSetImmediateExecution</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsetmaximumlength"><b>WdfDmaTransactionSetMaximumLength</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsetsingletransferrequirement"><b>WdfDmaTransactionSetSingleTransferRequirement</b></mshelp:link>
</td>
<td>1.19</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionsettransfercompletecallback"><b>WdfDmaTransactionSetTransferCompleteCallback</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionstopsystemtransfer"><b>WdfDmaTransactionStopSystemTransfer</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdmatransactionwdmgettransfercontext"><b>WdfDmaTransactionWdmGetTransferContext</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdpccancel"><b>WdfDpcCancel</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdpccreate"><b>WdfDpcCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdpcenqueue"><b>WdfDpcEnqueue</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdpcgetparentobject"><b>WdfDpcGetParentObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdpcwdmgetdpc"><b>WdfDpcWdmGetDpc</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdrivercreate"><b>WdfDriverCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdrivergetregistrypath"><b>WdfDriverGetRegistryPath</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriverisversionavailable"><b>WdfDriverIsVersionAvailable</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriverminiportunload"><b>WdfDriverMiniportUnload</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriveropenparametersregistrykey"><b>WdfDriverOpenParametersRegistryKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriverregistertraceinfo"><b>WdfDriverRegisterTraceInfo</b></mshelp:link>
</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriverretrieveversionstring"><b>WdfDriverRetrieveVersionString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfdriverwdmgetdriverobject"><b>WdfDriverWdmGetDriverObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoaddstaticchild"><b>WdfFdoAddStaticChild</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdogetdefaultchildlist"><b>WdfFdoGetDefaultChildList</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitallocandqueryproperty"><b>WdfFdoInitAllocAndQueryProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitallocandquerypropertyex"><b>WdfFdoInitAllocAndQueryPropertyEx</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitopenregistrykey"><b>WdfFdoInitOpenRegistryKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitqueryproperty"><b>WdfFdoInitQueryProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitquerypropertyex"><b>WdfFdoInitQueryPropertyEx</b></mshelp:link>
</td>
<td>1.13</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitsetdefaultchildlistconfig"><b>WdfFdoInitSetDefaultChildListConfig</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitseteventcallbacks"><b>WdfFdoInitSetEventCallbacks</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitsetfilter"><b>WdfFdoInitSetFilter</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoinitwdmgetphysicaldevice"><b>WdfFdoInitWdmGetPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdolockstaticchildlistforiteration"><b>WdfFdoLockStaticChildListForIteration</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoqueryforinterface"><b>WdfFdoQueryForInterface</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdoretrievenextstaticchild"><b>WdfFdoRetrieveNextStaticChild</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffdounlockstaticchildlistfromiteration"><b>WdfFdoUnlockStaticChildListFromIteration</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectgetdevice"><b>WdfFileObjectGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectgetfilename"><b>WdfFileObjectGetFileName</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectgetflags"><b>WdfFileObjectGetFlags</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectgetinitiatorprocessid"><b>WdfFileObjectGetInitiatorProcessId</b></mshelp:link>
</td>
<td>1.21
            </td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectgetrelatedfileobject"><b>WdfFileObjectGetRelatedFileObject</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdffileobjectwdmgetfileobject"><b>WdfFileObjectWdmGetFileObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfgetdriver"><b>WdfGetDriver</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfgettriageinfo"><b>WdfGetTriageInfo</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptacquirelock"><b>WdfInterruptAcquireLock</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptcreate"><b>WdfInterruptCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptdisable"><b>WdfInterruptDisable</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptenable"><b>WdfInterruptEnable</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptgetdevice"><b>WdfInterruptGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptgetinfo"><b>WdfInterruptGetInfo</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptqueuedpcforisr"><b>WdfInterruptQueueDpcForIsr</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptqueueworkitemforisr"><b>WdfInterruptQueueWorkItemForIsr</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptreleaselock"><b>WdfInterruptReleaseLock</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptreportactive"><b>WdfInterruptReportActive</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptreportinactive"><b>WdfInterruptReportInactive</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptsetextendedpolicy"><b>WdfInterruptSetExtendedPolicy</b></mshelp:link>
</td>
<td>1.9</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptsetpolicy"><b>WdfInterruptSetPolicy</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptsynchronize"><b>WdfInterruptSynchronize</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterrupttrytoacquirelock"><b>WdfInterruptTryToAcquireLock</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfinterruptwdmgetinterrupt"><b>WdfInterruptWdmGetInterrupt</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueueassignforwardprogresspolicy"><b>WdfIoQueueAssignForwardProgressPolicy</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuecreate"><b>WdfIoQueueCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuedrain"><b>WdfIoQueueDrain</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuedrainsynchronously"><b>WdfIoQueueDrainSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuefindrequest"><b>WdfIoQueueFindRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuegetdevice"><b>WdfIoQueueGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuegetstate"><b>WdfIoQueueGetState</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuepurge"><b>WdfIoQueuePurge</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuepurgesynchronously"><b>WdfIoQueuePurgeSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuereadynotify"><b>WdfIoQueueReadyNotify</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueueretrievefoundrequest"><b>WdfIoQueueRetrieveFoundRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueueretrievenextrequest"><b>WdfIoQueueRetrieveNextRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueueretrieverequestbyfileobject"><b>WdfIoQueueRetrieveRequestByFileObject</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuestart"><b>WdfIoQueueStart</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuestop"><b>WdfIoQueueStop</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuestopandpurge"><b>WdfIoQueueStopAndPurge</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuestopandpurgesynchronously"><b>WdfIoQueueStopAndPurgeSynchronously</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioqueuestopsynchronously"><b>WdfIoQueueStopSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistappenddescriptor"><b>WdfIoResourceListAppendDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistcreate"><b>WdfIoResourceListCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistgetcount"><b>WdfIoResourceListGetCount</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistgetdescriptor"><b>WdfIoResourceListGetDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistinsertdescriptor"><b>WdfIoResourceListInsertDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistremove"><b>WdfIoResourceListRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistremovebydescriptor"><b>WdfIoResourceListRemoveByDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcelistupdatedescriptor"><b>WdfIoResourceListUpdateDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistappendioreslist"><b>WdfIoResourceRequirementsListAppendIoResList</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistgetcount"><b>WdfIoResourceRequirementsListGetCount</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistgetioreslist"><b>WdfIoResourceRequirementsListGetIoResList</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistinsertioreslist"><b>WdfIoResourceRequirementsListInsertIoResList</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistremove"><b>WdfIoResourceRequirementsListRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistremovebyioreslist"><b>WdfIoResourceRequirementsListRemoveByIoResList</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistsetinterfacetype"><b>WdfIoResourceRequirementsListSetInterfaceType</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfioresourcerequirementslistsetslotnumber"><b>WdfIoResourceRequirementsListSetSlotNumber</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetallocandquerytargetproperty"><b>WdfIoTargetAllocAndQueryTargetProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetclose"><b>WdfIoTargetClose</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetcloseforqueryremove"><b>WdfIoTargetCloseForQueryRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetcreate"><b>WdfIoTargetCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetformatrequestforinternalioctl"><b>WdfIoTargetFormatRequestForInternalIoctl</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetformatrequestforinternalioctlothers"><b>WdfIoTargetFormatRequestForInternalIoctlOthers</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetformatrequestforioctl"><b>WdfIoTargetFormatRequestForIoctl</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetformatrequestforread"><b>WdfIoTargetFormatRequestForRead</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetformatrequestforwrite"><b>WdfIoTargetFormatRequestForWrite</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetgetdevice"><b>WdfIoTargetGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetgetstate"><b>WdfIoTargetGetState</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetopen"><b>WdfIoTargetOpen</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetpurge"><b>WdfIoTargetPurge</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetqueryforinterface"><b>WdfIoTargetQueryForInterface</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetquerytargetproperty"><b>WdfIoTargetQueryTargetProperty</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetsendinternalioctlotherssynchronously"><b>WdfIoTargetSendInternalIoctlOthersSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetsendinternalioctlsynchronously"><b>WdfIoTargetSendInternalIoctlSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetsendioctlsynchronously"><b>WdfIoTargetSendIoctlSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetsendreadsynchronously"><b>WdfIoTargetSendReadSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetsendwritesynchronously"><b>WdfIoTargetSendWriteSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetstart"><b>WdfIoTargetStart</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetstop"><b>WdfIoTargetStop</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetwdmgettargetdeviceobject"><b>WdfIoTargetWdmGetTargetDeviceObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetwdmgettargetfilehandle"><b>WdfIoTargetWdmGetTargetFileHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.15</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetwdmgettargetfileobject"><b>WdfIoTargetWdmGetTargetFileObject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfiotargetwdmgettargetphysicaldevice"><b>WdfIoTargetWdmGetTargetPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdflookasidelistcreate"><b>WdfLookasideListCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemoryassignbuffer"><b>WdfMemoryAssignBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorycopyfrombuffer"><b>WdfMemoryCopyFromBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorycopytobuffer"><b>WdfMemoryCopyToBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorycreate"><b>WdfMemoryCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorycreatefromlookaside"><b>WdfMemoryCreateFromLookaside</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorycreatepreallocated"><b>WdfMemoryCreatePreallocated</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfmemorygetbuffer"><b>WdfMemoryGetBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectacquirelock"><b>WdfObjectAcquireLock</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectaddcustomtype"><b>WdfObjectAddCustomType</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectaddcustomtypewithdata"><b>WdfObjectAddCustomTypeWithData</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectallocatecontext"><b>WdfObjectAllocateContext</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectcontextgetobject"><b>WdfObjectContextGetObject</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectcreate"><b>WdfObjectCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectdelete"><b>WdfObjectDelete</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectdereference"><b>WdfObjectDereference</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectdereferenceactual"><b>WdfObjectDereferenceActual</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectdereferencewithtag"><b>WdfObjectDereferenceWithTag</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectgetcustomtypedata"><b>WdfObjectGetCustomTypeData</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectgettypedcontext"><b>WdfObjectGetTypedContext</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectgettypedcontextworker"><b>WdfObjectGetTypedContextWorker</b></mshelp:link>
</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectiscustomtype"><b>WdfObjectIsCustomType</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectquery"><b>WdfObjectQuery</b></mshelp:link>
</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectreference"><b>WdfObjectReference</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectreferenceactual"><b>WdfObjectReferenceActual</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectreferencewithtag"><b>WdfObjectReferenceWithTag</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfobjectreleaselock"><b>WdfObjectReleaseLock</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoaddejectionrelationsphysicaldevice"><b>WdfPdoAddEjectionRelationsPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoclearejectionrelationsdevices"><b>WdfPdoClearEjectionRelationsDevices</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdogetparent"><b>WdfPdoGetParent</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitaddcompatibleid"><b>WdfPdoInitAddCompatibleID</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitadddevicetext"><b>WdfPdoInitAddDeviceText</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitaddhardwareid"><b>WdfPdoInitAddHardwareID</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitallocate"><b>WdfPdoInitAllocate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitallowforwardingrequesttoparent"><b>WdfPdoInitAllowForwardingRequestToParent</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitassigncontainerid"><b>WdfPdoInitAssignContainerID</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitassigndeviceid"><b>WdfPdoInitAssignDeviceID</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitassigninstanceid"><b>WdfPdoInitAssignInstanceID</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitassignrawdevice"><b>WdfPdoInitAssignRawDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitsetdefaultlocale"><b>WdfPdoInitSetDefaultLocale</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoinitseteventcallbacks"><b>WdfPdoInitSetEventCallbacks</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdomarkmissing"><b>WdfPdoMarkMissing</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoremoveejectionrelationsphysicaldevice"><b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdorequesteject"><b>WdfPdoRequestEject</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoretrieveaddressdescription"><b>WdfPdoRetrieveAddressDescription</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoretrieveidentificationdescription"><b>WdfPdoRetrieveIdentificationDescription</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpdoupdateaddressdescription"><b>WdfPdoUpdateAddressDescription</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpostdeviceinstall"><b>WdfPostDeviceInstall</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpostdeviceremove"><b>WdfPostDeviceRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpredeviceinstall"><b>WdfPreDeviceInstall</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpredeviceinstallex"><b>WdfPreDeviceInstallEx</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfpredeviceremove"><b>WdfPreDeviceRemove</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignmemory"><b>WdfRegistryAssignMemory</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignmultistring"><b>WdfRegistryAssignMultiString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignstring"><b>WdfRegistryAssignString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignulong"><b>WdfRegistryAssignULong</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignunicodestring"><b>WdfRegistryAssignUnicodeString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryassignvalue"><b>WdfRegistryAssignValue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryclose"><b>WdfRegistryClose</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistrycreatekey"><b>WdfRegistryCreateKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryopenkey"><b>WdfRegistryOpenKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryquerymemory"><b>WdfRegistryQueryMemory</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryquerymultistring"><b>WdfRegistryQueryMultiString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryquerystring"><b>WdfRegistryQueryString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryqueryulong"><b>WdfRegistryQueryULong</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryqueryunicodestring"><b>WdfRegistryQueryUnicodeString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryqueryvalue"><b>WdfRegistryQueryValue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryremovekey"><b>WdfRegistryRemoveKey</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistryremovevalue"><b>WdfRegistryRemoveValue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfregistrywdmgethandle"><b>WdfRegistryWdmGetHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestallocatetimer"><b>WdfRequestAllocateTimer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcancelsentrequest"><b>WdfRequestCancelSentRequest</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestchangetarget"><b>WdfRequestChangeTarget</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcomplete"><b>WdfRequestComplete</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcompletewithinformation"><b>WdfRequestCompleteWithInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcompletewithpriorityboost"><b>WdfRequestCompleteWithPriorityBoost</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcreate"><b>WdfRequestCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestcreatefromirp"><b>WdfRequestCreateFromIrp</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestformatrequestusingcurrenttype"><b>WdfRequestFormatRequestUsingCurrentType</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestforwardtoioqueue"><b>WdfRequestForwardToIoQueue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestforwardtoparentdeviceioqueue"><b>WdfRequestForwardToParentDeviceIoQueue</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetcompletionparams"><b>WdfRequestGetCompletionParams</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgeteffectiveiotype"><b>WdfRequestGetEffectiveIoType</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetfileobject"><b>WdfRequestGetFileObject</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetinformation"><b>WdfRequestGetInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetioqueue"><b>WdfRequestGetIoQueue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetparameters"><b>WdfRequestGetParameters</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetrequestormode"><b>WdfRequestGetRequestorMode</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetrequestorprocessid"><b>WdfRequestGetRequestorProcessId</b></mshelp:link>
</td>
<td>1.21
            </td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetstatus"><b>WdfRequestGetStatus</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestgetusermodeinitiatedio"><b>WdfRequestGetUserModeDriverInitiatedIo</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestimpersonate"><b>WdfRequestImpersonate</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestiscanceled"><b>WdfRequestIsCanceled</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestisfrom32bitprocess"><b>WdfRequestIsFrom32BitProcess</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestisfromusermodedriver"><b>WdfRequestIsFromUserModeDriver</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestisreserved"><b>WdfRequestIsReserved</b></mshelp:link>
</td>
<td>1.9</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestmarkcancelable"><b>WdfRequestMarkCancelable</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestmarkcancelableex"><b>WdfRequestMarkCancelableEx</b></mshelp:link>
</td>
<td>1.9</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestprobeandlockuserbufferforread"><b>WdfRequestProbeAndLockUserBufferForRead</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestprobeandlockuserbufferforwrite"><b>WdfRequestProbeAndLockUserBufferForWrite</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestrequeue"><b>WdfRequestRequeue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveactivityid"><b>WdfRequestRetrieveActivityId</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveinputbuffer"><b>WdfRequestRetrieveInputBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveinputmemory"><b>WdfRequestRetrieveInputMemory</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveinputwdmmdl"><b>WdfRequestRetrieveInputWdmMdl</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveoutputbuffer"><b>WdfRequestRetrieveOutputBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveoutputmemory"><b>WdfRequestRetrieveOutputMemory</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveoutputwdmmdl"><b>WdfRequestRetrieveOutputWdmMdl</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveunsafeuserinputbuffer"><b>WdfRequestRetrieveUnsafeUserInputBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestretrieveunsafeuseroutputbuffer"><b>WdfRequestRetrieveUnsafeUserOutputBuffer</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestreuse"><b>WdfRequestReuse</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestsend"><b>WdfRequestSend</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestsetactivityid"><b>WdfRequestSetActivityId</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestsetcompletionroutine"><b>WdfRequestSetCompletionRoutine</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestsetinformation"><b>WdfRequestSetInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestsetusermodedriverinitiatedio"><b>WdfRequestSetUserModeDriverInitiatedIo</b></mshelp:link>
</td>
<td></td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequeststopacknowledge"><b>WdfRequestStopAcknowledge</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestunmarkcancelable"><b>WdfRequestUnmarkCancelable</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestwdmformatusingstacklocation"><b>WdfRequestWdmFormatUsingStackLocation</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfrequestwdmgetirp"><b>WdfRequestWdmGetIrp</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfspinlockacquire"><b>WdfSpinLockAcquire</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfspinlockcreate"><b>WdfSpinLockCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfspinlockrelease"><b>WdfSpinLockRelease</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfstringcreate"><b>WdfStringCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfstringgetunicodestring"><b>WdfStringGetUnicodeString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdftimercreate"><b>WdfTimerCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdftimergetparentobject"><b>WdfTimerGetParentObject</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdftimerstart"><b>WdfTimerStart</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdftimerstop"><b>WdfTimerStop</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetconfiguredpipe"><b>WdfUsbInterfaceGetConfiguredPipe</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetconfiguredsettingindex"><b>WdfUsbInterfaceGetConfiguredSettingIndex</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetdescriptor"><b>WdfUsbInterfaceGetDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetendpointinformation"><b>WdfUsbInterfaceGetEndpointInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetinterfacenumber"><b>WdfUsbInterfaceGetInterfaceNumber</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetnumconfiguredpipes"><b>WdfUsbInterfaceGetNumConfiguredPipes</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetnumendpoints"><b>WdfUsbInterfaceGetNumEndpoints</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfacegetnumsettings"><b>WdfUsbInterfaceGetNumSettings</b></mshelp:link>
</td>
<td>1.5</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbinterfaceselectsetting"><b>WdfUsbInterfaceSelectSetting</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceallocandquerystring"><b>WdfUsbTargetDeviceAllocAndQueryString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicecreate"><b>WdfUsbTargetDeviceCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicecreateisochurb"><b>WdfUsbTargetDeviceCreateIsochUrb</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicecreateurb"><b>WdfUsbTargetDeviceCreateUrb</b></mshelp:link>
</td>
<td>1.11</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicecreatewithparameters"><b>WdfUsbTargetDeviceCreateWithParameters</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicecycleportsynchronously"><b>WdfUsbTargetDeviceCyclePortSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceformatrequestforcontroltransfer"><b>WdfUsbTargetDeviceFormatRequestForControlTransfer</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceformatrequestforcycleport"><b>WdfUsbTargetDeviceFormatRequestForCyclePort</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceformatrequestforstring"><b>WdfUsbTargetDeviceFormatRequestForString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceformatrequestforurb"><b>WdfUsbTargetDeviceFormatRequestForUrb</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicegetdevicedescriptor"><b>WdfUsbTargetDeviceGetDeviceDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicegetinterface"><b>WdfUsbTargetDeviceGetInterface</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicegetiotarget"><b>WdfUsbTargetDeviceGetIoTarget</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicegetnuminterfaces"><b>WdfUsbTargetDeviceGetNumInterfaces</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceisconnectedsynchronous"><b>WdfUsbTargetDeviceIsConnectedSynchronous</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicequerystring"><b>WdfUsbTargetDeviceQueryString</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicequeryusbcapability"><b>WdfUsbTargetDeviceQueryUsbCapability</b></mshelp:link>
</td>
<td>1.11</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceresetportsynchronously"><b>WdfUsbTargetDeviceResetPortSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceretrieveconfigdescriptor"><b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceretrievecurrentframenumber"><b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceretrieveinformation"><b>WdfUsbTargetDeviceRetrieveInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceselectconfig"><b>WdfUsbTargetDeviceSelectConfig</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceselectconfigtype"><b>WdfUsbTargetDeviceSelectConfigType</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdeviceselectsettingtype"><b>WdfUsbTargetDeviceSelectSettingType</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicesendcontroltransfersynchronously"><b>WdfUsbTargetDeviceSendControlTransferSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicesendurbsynchronously"><b>WdfUsbTargetDeviceSendUrbSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetdevicewdmgetconfigurationhandle"><b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeabortsynchronously"><b>WdfUsbTargetPipeAbortSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeconfigcontinuousreader"><b>WdfUsbTargetPipeConfigContinuousReader</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeformatrequestforabort"><b>WdfUsbTargetPipeFormatRequestForAbort</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeformatrequestforread"><b>WdfUsbTargetPipeFormatRequestForRead</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeformatrequestforreset"><b>WdfUsbTargetPipeFormatRequestForReset</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeformatrequestforurb"><b>WdfUsbTargetPipeFormatRequestForUrb</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeformatrequestforwrite"><b>WdfUsbTargetPipeFormatRequestForWrite</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipegetinformation"><b>WdfUsbTargetPipeGetInformation</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipegetiotarget"><b>WdfUsbTargetPipeGetIoTarget</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipegettype"><b>WdfUsbTargetPipeGetType</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeisinendpoint"><b>WdfUsbTargetPipeIsInEndpoint</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipeisoutendpoint"><b>WdfUsbTargetPipeIsOutEndpoint</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipereadsynchronously"><b>WdfUsbTargetPipeReadSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpiperesetsynchronously"><b>WdfUsbTargetPipeResetSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipesendurbsynchronously"><b>WdfUsbTargetPipeSendUrbSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipesetnomaximumpacketsizecheck"><b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipewdmgetpipehandle"><b>WdfUsbTargetPipeWdmGetPipeHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfusbtargetpipewritesynchronously"><b>WdfUsbTargetPipeWriteSynchronously</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfverifierdbgbreakpoint"><b>WdfVerifierDbgBreakPoint</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfverifierkebugcheck"><b>WdfVerifierKeBugCheck</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwaitlockacquire"><b>WdfWaitLockAcquire</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwaitlockcreate"><b>WdfWaitLockCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwaitlockrelease"><b>WdfWaitLockRelease</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwdmdevicegetwdfdevicehandle"><b>WdfWdmDeviceGetWdfDeviceHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwdmdrivergetwdfdriverhandle"><b>WdfWdmDriverGetWdfDriverHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstancecreate"><b>WdfWmiInstanceCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstancederegister"><b>WdfWmiInstanceDeregister</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstancefireevent"><b>WdfWmiInstanceFireEvent</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstancegetdevice"><b>WdfWmiInstanceGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstancegetprovider"><b>WdfWmiInstanceGetProvider</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiinstanceregister"><b>WdfWmiInstanceRegister</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiprovidercreate"><b>WdfWmiProviderCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiprovidergetdevice"><b>WdfWmiProviderGetDevice</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiprovidergettracinghandle"><b>WdfWmiProviderGetTracingHandle</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfwmiproviderisenabled"><b>WdfWmiProviderIsEnabled</b></mshelp:link>
</td>
<td>1.0</td>
<td></td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfworkitemcreate"><b>WdfWorkItemCreate</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfworkitemenqueue"><b>WdfWorkItemEnqueue</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfworkitemflush"><b>WdfWorkItemFlush</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
<tr>
<td>
<mshelp:link tabindex="0" keywords="wdf.wdfworkitemgetparentobject"><b>WdfWorkItemGetParentObject</b></mshelp:link>
</td>
<td>1.0</td>
<td>2.0</td>
</tr>
</table>

Send comments about this topic to Microsoft

