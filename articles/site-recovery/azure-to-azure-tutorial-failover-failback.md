---
title: Fail over and fail back Azure IaaS VMs replicated to a secondary Azure region for disaster recovery with the Azure Site Recovery service.
description: Learn how to fail over and fail back Azure VMs replicated to a secondary Azure region for disaster recovery, with the Azure Site Recovery service.
services: site-recovery
author: rayne-wiselman
manager: carmonm
ms.service: site-recovery
ms.topic: tutorial
ms.date: 12/27/2018
ms.author: raynew
ms.custom: mvc
---

# Fail over and Reprotect Azure VMs between Azure regions

The [Azure Site Recovery](site-recovery-overview.md) service contributes to your disaster recovery strategy by managing and orchestrating replication, failover, and failback of on-premises machines, and Azure virtual machines (VMs).

This tutorial describes how to fail over a single Azure VM to a secondary Azure region. After you've failed over, you fail back to the primary region when it's available. In this tutorial, you learn how to:

> [!div class="checklist"]
> * Fail over the Azure VM
> * Reprotect the secondary Azure VM, so that it replicates to the primary region.

> [!NOTE]
> This tutorial is intended to guide the user through the steps to fail over to a target region and back with minimum customization; in case you want to learn more about the various aspects associated with failover, including networking considerations, automation or troubleshooting, refer to the documents under 'How To' for Azure VMs.

## Prerequisites

- Make sure that you've completed a [disaster recovery drill](azure-to-azure-tutorial-dr-drill.md) to check everything is working as
expected.
- Verify the VM properties before you run the test failover. The VM must comply with [Azure requirements](azure-to-azure-support-matrix.md#replicated-machine-operating-systems).

## Run a failover to the secondary region

1. In **Replicated items**, select the VM that you want to fail over > **Failover**

   ![Failover](./media/azure-to-azure-tutorial-failover-failback/failover.png)

2. In **Failover**, select a **Recovery Point** to fail over to. You can use one of the
   following options:

   * **Latest** (default): This option processes all the data in the Site Recovery service and
     provides the lowest Recovery Point Objective (RPO).
   * **Latest processed**: This option reverts the virtual machine to the latest recovery point that
     has been processed by Site Recovery service.
   * **Custom**: Use this option to fail over to a particular recovery point. This option is useful
     for performing a test failover.

3. Select **Shut down machine before beginning failover** if you want Site Recovery to attempt to
   do a shutdown of source virtual machines before triggering the failover. Failover continues even
   if shutdown fails. Note that Site Recovery does not clean up source after failover.

4. Follow the failover progress on the **Jobs** page.

5. After the failover, validate the virtual machine by logging in to it. If you want to go another
   recovery point for the virtual machine, then you can use **Change recovery point** option.

6. Once you are satisfied with the failed over virtual machine, you can **Commit** the failover.
   Committing deletes all the recovery points available with the service. The **Change recovery
   point** option is no longer available.

## Reprotect the secondary VM

After failover of the VM, you need to reprotect it so that it replicates back to the primary region.

1. Make sure that the VM is in the **Failover committed** state, and check that the primary region is available, and you're able to create and access new resources in it.
2. In **Vault** > **Replicated items**, right-click the VM that's been failed over, and then select **Re-Protect**.

   ![Right-click to reprotect](./media/azure-to-azure-tutorial-failover-failback/reprotect.png)

2. Notice that the direction of protection, secondary to primary region, is already selected.
3. Review the **Resource group, Network, Storage, and Availability sets** information. Any
   resources marked (new) are created as part of the reprotect operation.
4. Click **OK** to trigger a reprotect job. This job seeds the target site with the latest data. Then, it replicates the deltas to the primary region. The VM is now in a protected state.

> [!NOTE]
> See the ["how to" section](https://docs.microsoft.com/azure/site-recovery/azure-to-azure-how-to-reprotect#what-happens-during-reprotection) for more details about the reprotection work flow and what happens during reprotection.


## Next steps
- Read [how to failback. ](azure-to-azure-tutorial-failback.md).
