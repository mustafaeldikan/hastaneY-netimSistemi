-- --------------------------------------------------------
-- Sunucu:                       127.0.0.1
-- Sunucu sürümü:                10.10.2-MariaDB - mariadb.org binary distribution
-- Sunucu İşletim Sistemi:       Win64
-- HeidiSQL Sürüm:               11.3.0.6295
-- --------------------------------------------------------

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET NAMES utf8 */;
/*!50503 SET NAMES utf8mb4 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;


-- hospital için veritabanı yapısı dökülüyor
CREATE DATABASE IF NOT EXISTS `hospital` /*!40100 DEFAULT CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci */;
USE `hospital`;

-- tablo yapısı dökülüyor hospital.admin
CREATE TABLE IF NOT EXISTS `admin` (
  `username` varchar(15) NOT NULL,
  `password` varchar(15) NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

-- hospital.admin: 1 rows tablosu için veriler indiriliyor
DELETE FROM `admin`;
/*!40000 ALTER TABLE `admin` DISABLE KEYS */;
INSERT INTO `admin` (`username`, `password`) VALUES
	('admin', 'admin');
/*!40000 ALTER TABLE `admin` ENABLE KEYS */;

-- tablo yapısı dökülüyor hospital.appointment
CREATE TABLE IF NOT EXISTS `appointment` (
  `dName` varchar(20) NOT NULL,
  `pName` varchar(15) NOT NULL,
  `room` int(11) NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

-- hospital.appointment: 0 rows tablosu için veriler indiriliyor
DELETE FROM `appointment`;
/*!40000 ALTER TABLE `appointment` DISABLE KEYS */;
/*!40000 ALTER TABLE `appointment` ENABLE KEYS */;

-- tablo yapısı dökülüyor hospital.doctor
CREATE TABLE IF NOT EXISTS `doctor` (
  `count` int(11) NOT NULL AUTO_INCREMENT,
  `date` varchar(10) NOT NULL,
  `id` varchar(10) NOT NULL,
  `name` varchar(30) NOT NULL,
  `age` int(5) NOT NULL,
  `gender` varchar(8) NOT NULL,
  `blood` varchar(4) NOT NULL,
  `dept` varchar(20) NOT NULL,
  `phone` varchar(15) NOT NULL,
  `email` varchar(30) NOT NULL,
  `status` varchar(10) NOT NULL,
  `address` varchar(20) NOT NULL,
  `room` int(11) NOT NULL,
  `username` varchar(20) NOT NULL,
  `password` varchar(30) NOT NULL,
  PRIMARY KEY (`count`)
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

-- hospital.doctor: 8 rows tablosu için veriler indiriliyor
DELETE FROM `doctor`;
/*!40000 ALTER TABLE `doctor` DISABLE KEYS */;
INSERT INTO `doctor` (`count`, `date`, `id`, `name`, `age`, `gender`, `blood`, `dept`, `phone`, `email`, `status`, `address`, `room`, `username`, `password`) VALUES
	(1, '02-04-2022', 'DR-1', 'Ali Alturk', 60, 'Male', 'A-', 'Medecine', '+905551237711', 'doctor@gmail.com', 'Single', 'Istanbul', 806, 'Ali', 'doctor'),
	(2, '31-01-2018', 'DR-2', 'Alaa Alaa', 32, 'Male', 'A+', 'Dental', '+905551237712', 'doctor@gmail.com', 'Married', 'Bursa', 202, 'Alaa', 'doctor'),
	(3, '12-12-2016', 'DR-3', 'Mohammad', 34, 'Male', 'AB-', 'Neurology', '+905551237713', 'doctor@gmail.com', 'Divorced', 'Mersin', 809, 'Mohammad', 'doctor'),
	(4, '21-08-2015', 'DR-4', 'Firas', 43, 'Male', 'B+', 'Nutrition', '+905551237714', 'doctor@gmail.com', 'Single', 'Hatay', 44, 'Firas', 'doctor'),
	(5, '09-08-2022', 'DR-5', 'Elif', 23, 'Female', 'O-', 'Gynaecology', '+905551237715', 'doctor@gmail.com', 'Single', 'Alanya', 909, 'Elif', 'doctor'),
	(6, '06-03-2016', 'DR-6', 'Faruk', 37, 'Male', 'B-', 'Cardiology', '+905551237716', 'doctor@gmail.com', 'Married', 'Antalya', 545, 'Faruk', 'doctor'),
	(7, '05-03-2015', 'DR-7', 'Zeynep', 28, 'Female', 'O+', 'Haematology', '+905551237717', 'doctor@gmail.com', 'Married', 'Tekerdag', 23, 'Zeynep', 'doctor'),
	(8, '21-12-2022', 'DR-8', 'Tavfik', 44, 'Male', 'B-', 'Microbiology', '+905551237718', 'doctor@gmail.com', 'Married', 'Urfa', 777, 'Tavfik', 'doctor');
/*!40000 ALTER TABLE `doctor` ENABLE KEYS */;

-- tablo yapısı dökülüyor hospital.patient
CREATE TABLE IF NOT EXISTS `patient` (
  `count` int(11) NOT NULL AUTO_INCREMENT,
  `date` varchar(10) NOT NULL,
  `id` varchar(20) NOT NULL,
  `name` varchar(20) NOT NULL,
  `age` int(5) NOT NULL,
  `gender` varchar(10) NOT NULL,
  `address` varchar(20) NOT NULL,
  `phone` varchar(20) NOT NULL,
  `status` varchar(10) NOT NULL,
  `disease` varchar(20) NOT NULL,
  `room` int(11) NOT NULL,
  PRIMARY KEY (`count`)
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

-- hospital.patient: 4 rows tablosu için veriler indiriliyor
DELETE FROM `patient`;
/*!40000 ALTER TABLE `patient` DISABLE KEYS */;
INSERT INTO `patient` (`count`, `date`, `id`, `name`, `age`, `gender`, `address`, `phone`, `status`, `disease`, `room`) VALUES
	(1, '09-06-2018', 'P-1', 'Bilal', 21, 'Male', 'Esenler', '+905552227722', 'Single', 'Dengue', 102),
	(2, '03-05-2017', 'P-2', 'Nur', 50, 'Male', 'Fatih', '+905552227723', 'Married', 'Jondish', 201),
	(3, '22-12-2017', 'P-3', 'Burak', 27, 'Male', 'Merter', '+905552227724', 'Married', 'Tyfoyed', 305),
	(4, '23-12-2022', 'P-4', 'Mejd', 25, 'Male', 'Uskudar', '+905552227725', 'Single', 'flu', 105);
/*!40000 ALTER TABLE `patient` ENABLE KEYS */;

-- tablo yapısı dökülüyor hospital.receptionist
CREATE TABLE IF NOT EXISTS `receptionist` (
  `count` int(11) NOT NULL AUTO_INCREMENT,
  `joining` varchar(15) NOT NULL,
  `id` varchar(15) NOT NULL,
  `name` varchar(30) NOT NULL,
  `age` int(5) NOT NULL,
  `gender` varchar(10) NOT NULL,
  `blood` varchar(4) NOT NULL,
  `email` varchar(40) NOT NULL,
  `phone` varchar(17) NOT NULL,
  `address` varchar(30) NOT NULL,
  `status` varchar(10) NOT NULL,
  `username` varchar(20) NOT NULL,
  `password` varchar(30) NOT NULL,
  PRIMARY KEY (`count`)
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

-- hospital.receptionist: 5 rows tablosu için veriler indiriliyor
DELETE FROM `receptionist`;
/*!40000 ALTER TABLE `receptionist` DISABLE KEYS */;
INSERT INTO `receptionist` (`count`, `joining`, `id`, `name`, `age`, `gender`, `blood`, `email`, `phone`, `address`, `status`, `username`, `password`) VALUES
	(1, '23-04-2013', 'REC-1', 'Ali', 21, 'Male', 'O+', 'receptionist@gmail.com', '+905551235566', 'Esenler', 'Single', 'Ali', 'RECEP'),
	(2, '23-06-2018', 'REC-2', 'Mahrus', 24, 'Male', 'A-', 'receptionist@gmail.com', '+905551235567', 'Fatih', 'Married', 'Mahrus', 'RECEP'),
	(3, '12-06-2019', 'REC-3', 'Ahmet', 24, 'Male', 'AB-', 'receptionist@gmail.com', '+905551235568', 'Uskudar', 'Single', 'Ahmet', 'RECEP'),
	(4, '07-12-2020', 'REC-4', 'Can', 34, 'Male', 'O+', 'receptionist@gmail.com', '+905551235569', 'Eyup', 'Married', 'Can', 'RECEP'),
	(5, '23-12-2022', 'REC-5', 'Samir', 44, 'Male', 'AB-', 'receptionist@gmail.com', '+905551235570', 'Merter', 'Single', 'Samir', 'RECEP');
/*!40000 ALTER TABLE `receptionist` ENABLE KEYS */;

/*!40101 SET SQL_MODE=IFNULL(@OLD_SQL_MODE, '') */;
/*!40014 SET FOREIGN_KEY_CHECKS=IFNULL(@OLD_FOREIGN_KEY_CHECKS, 1) */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40111 SET SQL_NOTES=IFNULL(@OLD_SQL_NOTES, 1) */;
