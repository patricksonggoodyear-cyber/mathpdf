# Number Theory Appendices — Editorial Progress

- Repository: patricksonggoodyear-cyber/mathpdf
- Branch: main
- Scope: materials/数论讲义翻译/ Appendix A, B (translation proofreading); Appendix C (translation)
- Source files: Appendix_A.md, Appendix B.md, Appendix C.md
- Chinese files: Appendix_A.zh-CN.md, Appendix_B.zh-CN.md, Appendix_C.zh-CN.md
- Translation file naming follows the existing zh-CN convention rather than introducing a parallel .zh.md file.

## Completed and committed

- Appendix A, section A.1: checked Euclidean division degree-reduction step against Chinese text; corrected English OCR/transcription error from degree < deg g to degree < deg f. Commit 9598d37439b8a8ff32a0404fa10f63425e8774af.
- Appendix C: initial Chinese translation from title through the paragraph preceding Problem C.1.1, including Definitions C.1.1–C.1.3; unresolved mathematics retained and reported. Commit aae8a541f9269fac6eea9c384830a774856fe7d9.

## Partially reviewed, NOT completed

- Appendix A: compared opening of A.1 and early polynomial division proof to Chinese; remainder requires line-by-line review.
- Appendix B: compared opening B.1 and symmetric polynomial theorem proof to Chinese; remainder requires line-by-line review. The English proof's ordinary-degree claim 'deg g <= deg f' and its inductive degree bound should be mathematically checked, including use of weighted degrees.
- Appendix C: C.1 is incomplete; resume translation at 'Problem C.1.1'. Remaining C subsections untouched.

## Unresolved issues

- Appendix C, Definition C.1.1: additive identity lacks '=u'; additive inverse axiom omitted; Z/p^nZ generally not an F_p vector space for n>1; right-scalar notation u(a+b) inconsistent with preceding convention.
- Appendix A, Remark A.1.1: original makes an assertion that both {0} and empty set are bases of {0} if the zero ring were a field; check what vector space conventions the author intends.
- Appendix B: degree bounds in fundamental theorem proof need verification.

## Terminology

- field: 域
- polynomial: 多项式
- symmetric polynomial: 对称多项式
- elementary symmetric polynomial: 初等对称多项式
- vector space: 向量空间
- scalar: 标量
- linearly independent: 线性无关
- basis: 基

## Next action

1. Continue translation of Appendix C from Problem C.1.1, moving the temporary uncertainty report to the final end of the complete translation.
2. Continue complete English-Chinese comparisons of Appendices A and B, one complete mathematical unit at a time.
3. Re-fetch SHA before updates; commit reviewed changes to main.
4. Final check all definitions, formulas, footnotes, cross-references and Obsidian/MathJax syntax.


## Checkpoint 2026-11-04 — continuation

- Completed Chinese translation of Appendix C section C.1, through Proposition C.1.4, commit b6eaa73d2e89f412788e8665efc383877e2ab3ff.
- Translated the beginning of C.2 through discussion of Lagrange interpolation, commit 24a3173c2e09197604aa7da2bd761cce589d6cfd.
- Source issues noted in Chinese uncertainty report: incomplete vector-space axioms, invalid F_p-vector-space example, integer cow weights induction argument, corrupted elimination coefficient indices, power-versus-iteration ambiguity, finite-field characteristic proof, interpolation coordinates.
- The preceding Current Task / Pending text is superseded for Appendix C: C.1 is now translated; C.2 is partially translated. Resume at 'We come back to more abstract considerations. Given the bases...' in the English Appendix C.md (matrix representation), continuing through C.2 and later sections.
- Appendix A and B whole-document translation checking is still incomplete and must be performed separately, not marked completed.
- Review the Chinese Appendix C uncertainty report and place unique Obsidian block anchors for outstanding points before finalizing.
- MathJax rendering has not yet been tested in Obsidian.
