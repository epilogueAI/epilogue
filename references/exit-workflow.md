# Clean Exit Workflow

This document defines the exact, safe process for planning and executing a portfolio wind-down.

## Goal
Help the user close a chapter cleanly: realize positions, claim residual value, minimize unnecessary risk and cost, and produce a final Exit Report.

## Phase 0 — Intake (always start here)

1. Confirm the scope:
   - Full portfolio exit, or only specific chains / positions / tokens?
   - Any positions that must be kept (long-term holds, legacy, etc.)?
   - Time preference: urgent / normal / patient (affects slippage tolerance).
   - Tax jurisdiction or reporting needs? (optional)

2. Gather current state using Bankr native tools only:
   - Portfolio balances + PnL across all relevant chains
   - Open limit / stop / DCA / TWAP orders
   - Papertrade / Hyperliquid / Avantis positions
   - Pending creator fees, reflections, staking rewards, Merkl, etc.
   - Locked liquidity, vesting, or time-locked assets
   - Any open NFT listings or pending mints

3. Present a clear summary of what was found before proposing any plan.

## Phase 1 — Analysis & Plan

1. Categorize holdings:
   - Liquid & easy to exit
   - Illiquid / thin liquidity (high slippage risk)
   - Locked / vesting / staked (time or unlock required)
   - Residual claims (fees, rewards)

2. Propose a staged exit plan with this structure:

   **Stage A — Residual Claims**  
   Claim all pending fees, reflections, staking rewards first.

   **Stage B — High-risk / High-leverage**  
   Close or reduce Papertrade / perp positions (priority if liquidation risk exists).

   **Stage C — Liquid tokens**  
   Swap or transfer according to user preference (to USDC / ETH / stable / specific wallet).

   **Stage D — Illiquid or special assets**  
   Flag thin liquidity, recommend limit orders or patience, or leave as-is.

   **Stage E — Final sweep**  
   Any remaining dust, gas tokens, or cleanup.

3. For every recommended action show:
   - What will happen
   - Estimated impact (slippage, gas, value)
   - Risk level (Low / Medium / High)
   - Whether it is irreversible

4. **Never execute anything in this phase.** Only present the plan and wait for explicit confirmation.

## Phase 2 — Confirmation Gate

Before any write action:
- Restate the exact actions the user is approving.
- Ask for clear confirmation (e.g. “Confirm Stage A + B” or “Confirm full plan”).
- If the user says “just do it” without specifics, ask them to confirm the stages or list the actions.

## Phase 3 — Execution (only after confirmation)

- Execute one stage (or one logical group) at a time.
- After each stage, report results and remaining plan.
- If any step fails or returns unexpected results, stop and report before continuing.
- Prefer Bankr native swap / transfer / close tools. Do not invent external routers.

## Phase 4 — Final Exit Report

After the agreed stages are complete (or the user stops):
- Generate a structured Exit Report (see `report-templates.md`).
- Offer to save it as a file in the user’s Bankr filesystem.
- Optionally offer a short narrative “Chapter closed” summary.

## Edge Cases

- User wants to keep some positions → mark them as “Excluded” and never touch them.
- Extremely thin liquidity → recommend limit order or “leave for later” instead of market sell.
- Open perps near liquidation → prioritize risk reduction and clearly state urgency.
- Missing data → say what is missing and do not invent numbers.
