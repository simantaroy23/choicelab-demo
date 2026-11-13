# ChoiceLab virtual store (interactive prototype)

**Try it:** https://simantaroy23.github.io/choicelab-demo/

A shopping simulation for studying how young adults who use only e-cigarettes (ENDS) respond to U.S. e-cigarette policies. Participants make choices in a simulated store with a real budget they get to keep. Choices are simulated purchases, not observed real-world tobacco use.

## Study design (four-arm randomized)

1. Eight screening and intake questions: age, usual device, flavor and nicotine strength, days vaped, weekly spend on **all** tobacco and nicotine products, usual purchase place, and past-30-day use of other products. Eligibility (exclusive ENDS users aged 21–45) is set in `CONFIG.eligibility` in `index.html`.
2. Two shopping trips in one licensed store (walk-in or online, matched to where the person usually buys), with the same budget on both:
   - Trip 1: baseline (current market), identical for every group.
   - Trip 2: one randomly assigned policy (1:1:1:1):
     - **A** E-cigarette flavor restriction (tobacco flavor only)
     - **B** E-cigarette nicotine limit, 2% (20 mg/mL); fruit and mint stay available
     - **C** Pictorial nicotine-addiction warnings on e-cigarettes (cigarette packs unchanged)
     - **D** E-cigarette price increase, +50% on all ENDS products
3. Each trip: buy e-cigarettes, cigarettes, cigarillos, nicotine pouches or nicotine gum, buy nothing, or report getting products from another source (where, what, optional amount). One trip is paid out as a bonus.

## Modes and URL parameters

- Demo (default): reviewer start page, example answers, choice of group, researcher view and CSV export. Rows are labeled `data_mode = demo`.
- Study: `?mode=study&pid=<ID>` skips the start page, has no example answers or researcher view, and keeps the same group for an ID on reload.
- Group assignment: `group=A|B|C|D` (passed by a survey platform's randomizer) > `seq=<n>` (permuted blocks of 4) > group stored for this ID > simple random.
- Data: in study mode, the completed record (participant, trip and item rows) is POSTed as JSON to `CONFIG.dataEndpoint`; nothing is sent until that is set.

## Notes

- All stores, brands and products are fictional. Images are AI-generated. E-cigarette warnings use FDA's required nicotine statement with an illustration.
- English and Spanish.
