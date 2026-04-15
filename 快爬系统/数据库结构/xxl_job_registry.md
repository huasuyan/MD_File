---
created: 2026-04-15T10:55:14+08:00
modified: 2026-04-15T10:57:46+08:00
---
/*
 Navicat Premium Data Transfer

 Source Server         : Web-Clawer
 Source Server Type    : MySQL
 Source Server Version : 80045 (8.0.45)
 Source Host           : 101.42.47.30:3306
 Source Schema         : xxl-job

 Target Server Type    : MySQL
 Target Server Version : 80045 (8.0.45)
 File Encoding         : 65001

 Date: 15/04/2026 10:52:41
*/

SET NAMES utf8mb4;
SET FOREIGN_KEY_CHECKS = 0;

-- ----------------------------
-- Table structure for xxl_job_registry
-- ----------------------------
DROP TABLE IF EXISTS `xxl_job_registry`;
CREATE TABLE `xxl_job_registry`  (
  `id` bigint NOT NULL AUTO_INCREMENT,
  `registry_group` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `registry_key` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `registry_value` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `update_time` datetime NULL DEFAULT NULL,
  PRIMARY KEY (`id`) USING BTREE,
  UNIQUE INDEX `i_g_k_v`(`registry_group` ASC, `registry_key` ASC, `registry_value` ASC) USING BTREE
) ENGINE = InnoDB AUTO_INCREMENT = 3616 CHARACTER SET = utf8mb4 COLLATE = utf8mb4_0900_ai_ci ROW_FORMAT = DYNAMIC;

SET FOREIGN_KEY_CHECKS = 1;
