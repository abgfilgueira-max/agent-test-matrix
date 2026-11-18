# Test matrix for a conversational collections agent

The template I use before a conversational agent talks to real customers. It is a method, not code: a list of cases, what should happen in each one, and the rules that decide whether we go live.

## How I use it

1. Write the go / no-go criteria **before** testing. If they are written after, they bend to the result.
2. Test in a separate environment with simulated customers. Nothing is loaded on the real portfolio until critical tickets are closed.
3. Run every case in `test_matrix.csv` and record expected against obtained.
4. Open one ticket per failure, linked to the exact conversation.
5. After each fix, run the whole block again (regression).

## Severity

| Level | Meaning | Effect |
|---|---|---|
| Blocking | Privacy, wrong amount, wrong person | No go until fixed and retested |
| Serious | The customer cannot complete the agreement | No go if more than one is open |
| Minor | Wording, tone, a slow answer | Goes to the backlog |

## Go / no-go criteria

- Zero blocking cases open.
- Every agreement is recorded with the amount and date the customer accepted.
- The agent never gives debt details to anyone other than the account holder.
- Hand-off to a person works when the agent cannot solve the case.
- A do-not-contact request is honoured on every channel.

## Blocks

Identification, negotiation, payment methods, hand-off, operation, and adversarial cases (prompt injection, a change of identity in the middle of the conversation).

All names and numbers in the file are invented.
