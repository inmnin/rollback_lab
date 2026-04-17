# rollback_lab backup

This repository contains a filtered backup of `/root/autodl-tmp/jkh` created on `2026-04-17`.

Included:
- Backup metadata under `metadata/`
- Split compressed backup archives under `backup_parts/`

Excluded from the archive:
- `/root/autodl-tmp/jkh/.cache/huggingface`
- `/root/autodl-tmp/jkh/.cache/pip`
- `/root/autodl-tmp/jkh/.cache/uv`
- `/root/autodl-tmp/jkh/.conda`
- `/root/autodl-tmp/jkh/.local/lib`
- Files larger than `1 GiB`

Environment bodies under `.conda` and related package caches are not uploaded.
Their environment names and package versions are recorded in `metadata/virtualenv_inventory.txt`.

To restore:

```bash
cat backup_parts/jkh_backup_20260417.tar.zst.part-* > /tmp/jkh_backup_20260417.tar.zst
tar --zstd -xf /tmp/jkh_backup_20260417.tar.zst -C /
```
