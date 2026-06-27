# Current Tasks

- [ ] Review and commit Sprint-13 closure governance updates
- [ ] Review and commit the Sprint-14 roadmap and closure governance updates
- [ ] Review and commit the Sprint-15 closure governance updates
- [ ] Commit the separate `devlog_cli` Sprint-13 implementation if the learner wants to preserve it
- [ ] Review and commit the separate `rust_mechanics_lab` Sprint-14 implementation if the learner wants to preserve it
- [ ] Preserve the Teacher direct review plus Codex formal validation collaboration model
- [ ] Carry forward Sprint-14 teaching-process corrections: terminology format, validation question quality, `RefCell` explanation depth, recommended test names, and field-access auto-deref
- [ ] Compare normal `Vec<Record>` mutation through `&mut self` with `RefCell<Vec<Record>>` for APIs that only have `&self`, such as fake recorders or test doubles
- [ ] Reinforce that `&T` is `Copy`, while `&mut T` is not `Copy` because it represents exclusive mutable access
- [ ] Reinforce the analogy that `&Path` roughly corresponds to `&str`, while `PathBuf` roughly corresponds to `String`
- [ ] Reinforce `HashSet` as a direct duplicate-detection tool
- [ ] Revisit stricter persisted-data design using raw or persisted structs instead of public `Deserialize` on trusted public types
- [ ] Add focused file/storage test coverage when justified by future approved scope
- [ ] Revisit `Display` and `std::error::Error` for public error types
- [ ] Revisit overflow-safe id generation, including `max_id + 1` and `next_id += 1`
- [ ] Preserve Sprint-07 as a failed / abnormal sprint record and do not credit Sprint-07 learning progress
- [ ] Keep governance repository validation and learning-project validation separate
- [ ] Do not start, draft, or authorize Sprint-16 without a separate approved workflow
