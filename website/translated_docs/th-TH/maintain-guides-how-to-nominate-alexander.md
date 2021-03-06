---
id: maintain-guides-how-to-nominate-alexander
title: การเป็นผู้เสนอชื่อ (Nominator) บนเครือข่าย Alexander
sidebar_label: การเป็นผู้เสนอชื่อ (Nominator) บนเครือข่าย Alexander
---

คู่มือแนะนำนี้จะสอนคุณเกี่ยวกับวิธีการเสนอชื่อผู้ตรวจสอบโดยการล็อค DOT เพื่อให้คุณสามารถมีส่วนร่วมในระบบการเลือกผู้ตรวจสอบและรับ DOT เพิ่มเป็นผลตอบแทน

คู่มือนี้ได้รับการอัพเดตสำหรับเครือข่ายทดลอง Alexander และ Polkadot release PoC-4

## สร้างบัญชีประเภท `stash` และ `controller`

เราจะสมมติว่าคุณจะเริ่มต้นด้วยสองบัญชีใหม่ คลิก [ ที่นี่ ](learn-staking#accounts) เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับความหมายของบัญชีประเภท ` stash ` และ ` controller `

ขั้นตอนแรกคือการสร้างบัญชีสองอันโดยไปที่แท็บ *Accounts* บน Polkadot Dashboard และคลิกที่ [*Add account*](https://polkadot.js.org/apps/#/accounts) อย่าลืมใส่ `stash` และ `controller` ในชื่อบัญชีของคุณเพื่อช่วยในการแยกแยะ

![Creating an account](assets/guides/how-to-nominate/polkadot-dashboard-create-account.jpg)

เมื่อคุณสร้างบัญชีเสร็จแล้ว คุณต้องการ DOT จำนวนนึง กรุณาอ่าน [วิธีการขอ DOTs](learn-DOT#getting-testnet-dots) สำหรับคำแนะนำในการของ DOT สำหรับเครือข่ายทดลอง แต่ละบัญชีของคุณควรมีอย่างน้อย 150 milliDOTs เพื่อให้พอสำหรับการฝากเงินและค่าธรรมเนียมการทำธุรกรรม

## การเสนอชื่อ

ได้เวลาแล้วสำหรับการตั้งค่าบัญชีเสนอชื่อของเรา เราต้องทำสิ่งต่อไปนี้:
- ทำการล็อค DOT ของบัญชี `stash` DOT เหล่านี้จะถูกวางเป็นหลักประกันเพื่อความปลอดภัยของเครือข่ายและอาจถูกยึดได้
- เลือกบัญชี `controller` บัญชีนี้จะเป็นบัญชีที่ตัดสินใจว่าเริ่มหรือหยุดการเสนอชื่อตอนไหน

ก่อนแรกไปที่ส่วน [Staking > Account actions](https://polkadot.js.org/apps/#/staking/actions) และคลิกที่ปุ่ม "New Stake"

![dashboard bonding](assets/guides/how-to-nominate/polkadot-dashboard-bonding.jpg)

- **Stash account** - เลือกบัญชี `stash` ที่เราจะทำการวางเงินประกันจำนวน 100 milliDOTs ควรเช็คให้แน่ใจว่าบัญชีดังกล่าวมีเงินเพียงพอ
- **Controller account** - เลือกบัญชี `controller` จะสร้างขึ้นก่อนหน้านี้
- **Value bonded** - จำนวน DOT จากบัญชี `stash` ที่ต้องการจะล็อคเป็นเงินประกัน คุณสามารถเพิ่มจำนวนเงินประกันได้ภายหลัง แต่การถอนเงินประกันจะต้องรอจนกว่าระยะเวลาประกันเสร็จสิ้น (หลายเดือน ณ ขณะที่เขียนบทความนี้)
- **Payment destination** - เงินรางวัลจะถูกส่งไปที่นี่ อ่านข้อมูลเพิ่มเติมได้ [ที่นี่](learn-staking#reward-distribution).

หลังจากกรอกทุกอย่างถูกต้อง คลิก `Bond` และทำการเซ็น transaction (โดยใช้บัญชี `stash`) คุณจะเห็นอย่างดังกล่าวนี้ ไม่ต้องสนใจปุ่ม `Set Session Key` มันจะมีประโยชน์ก็ต่อเมื่อคุณต้องการตรวจสอบซึ่งเราไม่จำเป็นต้องใช้ในคู่มือนี้

![dashboard overview](assets/guides/how-to-nominate/polkadot-dashboard-set-session-key.jpg)

## การเสนอชื่อผู้ตรวจสอบ

ไปที่แท็บ *Staking Overview* บนหน้า Staking ของ Polkadot Dashboard ทางด้านซ้ายคุณจะเห็นรายการผู้ตรวจสอบ (ทางด้านขวาคือผู้ตรวจสอบที่สนใจที่จะเข้าร่วมกลุ่มผู้ตรวจสอบ คุณไม่ต้องสนใจพวกนี้ตอนนี้) จากรายการผู้ตรวจสอบ ให้คุณเลือกคนที่คุณอยากจะเสนอชื่อและทำการคัดลอก address ของเขาเก็บไว้ (โดยคลิกที่ identicon) หรือจะเพิ่มบัญชีเขาลงใน Address book ของคุณ

![Validators](assets/guides/how-to-nominate/validators.png)

ไปที่แท็บ *Account Actions* และคลิกปุ่ม `Nominate` กรอกข้อมูลในฟิลด์ว่างด้วย address ของผู้ตรวจสอบที่คุณเลือกที่จะเสนอชื่อ หลังจากเซ็นและส่ง transaction ของคุณแล้ว คุณจะเห็นปุ่ม `Stop Nominating` และบัญชีที่คุณกำลังเสนอชื่อในส่วน `Nominating` การเสนอชื่อของคุณจะมีผลในยุค (era) ถัดไป (ซึ่งอาจใช้เวลาถึงหนึ่งชั่วโมง)

![Nominating](assets/guides/how-to-nominate/nominating.jpg)

**ยินดีด้วย​!** คุณได้เป็นผู้เสนอชื่อแล้ว

ถ้าคุณกลับไปที่แท็บ *Staking Overview* หลังจาก era มีการเปลี่ยนแปลง และเลื่อนจนกว่าจะเจอผู้ตรวจสอบของคุณ คุณจะเห็นบัญชี `stash` ของคุณเป็นรายชื่อผู้เสนอชื่อของผู้ตรวจสอบนั้น

![Nominating2](assets/guides/how-to-nominate/nominating2.jpg)

## วิธีการหยุดเสนอชื่อ

หากต้องการจะหยุดการเสนอชื่อ เพียงแค่ไปแท็บ *Account Actions* และคลิกปุ่ม `Stop Nominating` บัญชีของคุณจะถูกเซ็ทเป็น `chill` และใน era ถัดไปจะยกเลิกการเสนอชื่อของผู้ตรวจสอบ ขั้นตอนนี้อาจใช้เวลาถึงหนึ่งชั่วโมงกว่าจะเห็นผล
