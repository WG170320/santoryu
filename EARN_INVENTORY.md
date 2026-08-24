# Earn feature inventory (parity guardrail — delete after dashboard refactor)

Every user-facing feature currently produced by `render()` + sub-pages, with its
builder and gate, and the tab it must live in after the refactor. Check each off
as it lands in its destination tab.

| Feature | Builder | Gate | Destination |
|---|---|---|---|
| Header: brand + balance pill + daily check-in icon | `render` head + `openDailyDialog` | always | shell |
| Ban warning | inline (`banwarn`) | `account.earnBanned` | Home top |
| Cloner warning | inline (`banwarn`) | `state.cloned` | Home top |
| Profile card (avatar/name/invite code/total earned) | inline `.profile` | always | Home |
| Withdraw banner -> Withdraw page | `withdrawBanner` / `openWithdrawPage` / `paintWithdraw` | always | Home |
| Invite hero (conditional +perInvite + status ledger) | `inviteHero` | always | Invite |
| Tongits hero + Tongits page | `tongitsHero` / `renderTongitsPage` | config.tongits* | Home Featured |
| Redeem entry + redeem dialog | `redeemEntry` / `openRedeemDialog` | always | Home Featured |
| Tournament banner + tournament page | `updateBanner` / `openTournament` | `tournament status==='open'` | Home Featured |
| Jogos Play&Earn hero (step 1) | inline `pehero` | `config.jogosEnabled && !jogosClaimed` | Home Featured |
| Jogos Play&Earn round 2 | inline `pehero2` | `jogosClaimed && !jogosClaimed2 && native` | Home Featured |
| Daily check-in dialog | `openDailyDialog` | `dailyAvailable` | shell/Home |
| Giveaway hero | `giveawayHero` | tasks match giveaway | Tasks top |
| Gear mission hero | `gearMissionHero` | `task.hero && usage` | Tasks (Download) |
| Task rows (comment/usage/review/social/plain) | `appendTasks` | `tasks[]` | Tasks (Download/Other) |
| Activity: Withdrawal history | `openHistory` | always | Home |
| Activity: Friends you invited | `openInvited` | always | Invite |
| Legal footer: Terms/Data Policy/Delete | `openInfo` / `openDelete` | always | Home |
