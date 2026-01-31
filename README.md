r
# =============================================================================
# SPOT - buildKriging: مرحله (K-2) نرمال‌سازی داده‌های ورودی
# منبع: بخش 4.6.5 کتاب Forrester et al. (2008)
# =============================================================================

## (K-2) Normalize input data
# تنظیم بازه هدف برای نرمال‌سازی (پیش‌فرض [0, 1])
fit$normalizeymin <- 0
fit$normalizeymax <- 1

# نرمال‌سازی ماتریس x با تابع normalizeMatrix
res <- normalizeMatrix(fit$x, ymin = fit$normalizeymin, ymax = fit$normalizeymax)

# ذخیره ماتریس نرمال‌شده و حدود هر ستون
fit$scaledx        <- res$y          # ماتریس x نرمال‌شده (هر ستون در [0, 1])
fit$normalizexmin  <- res$xmin       # حداقل هر ستون x اصلی
fit$normalizexmax  <- res$xmax       # حداکثر هر ستون x اصلی
