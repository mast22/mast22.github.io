+++
title = "Первый пост"
description = "Проверяю как работает SSR"
date = "2021-05-30"
+++

FROM DOCKER

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

```rust
use crate::vec3::Vec3;

#[derive(Debug, Copy, Clone)]
pub struct Ray {
    origin: Vec3, // Расположение
    direction: Vec3, // Направление
}

impl Ray {
    pub fn ray(origin: Vec3, direction: Vec3) -> Ray {
        Ray {
            origin,
            direction,
        }
    }

    pub fn origin(self) -> Vec3 {
        self.origin
    }

    pub fn direction(self) -> Vec3 {
        self.direction
    }

    pub fn at(self, t: f32) -> Vec3 {
        self.origin + self.direction * t
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_ray_origin() {}

    #[test]
    fn test_ray_direction() {}

    #[test]
    fn test_ray_point_at_parameter() {}
}
```
