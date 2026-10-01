# AGENTS — virtfoundry/.github

Perfil e defaults da org GitHub VirtFoundry (`profile/README.md`).

## Cursor Team Kit

Repos da org (`core`, `operator`, `helm-charts`, `terraform-provider-virtfoundry`) usam o plugin **cursor-team-kit**:

| Situação | Skill |
|----------|--------|
| Branch + PR | `new-branch-and-pr` / `review-and-ship` |
| CI | `fix-ci` + `loop-on-ci` |
| PR legível | `make-pr-easy-to-review` |
| Typecheck | `check-compiler-errors` |
| Limpar noise de AI | `deslop` |

Rules: `typescript-exhaustive-switch`, `no-inline-imports`.

## VirtFoundry (org)

- SemVer produto **0.9.x**; Terraform provider mantém série própria.
- Em **todo** fechamento de versão: bump `profile/README.md` (landing da org) + pins no site GitHub Pages (`helm-charts/docs/**`). Sempre ficam atrasados se o release PR não tocar aqui.
- Testes no **homelab** — nunca Kind como gate.
- Preview sem commit / tag / release só com pedido explícito do maintainer.
- Cada repo tem seu próprio `AGENTS.md` na raiz — preferir aquele ao editar código.

## Docs

- [profile/README.md](profile/README.md) — landing da org
