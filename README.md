disp('--- Chuong Trinh Tinh Ung Suat Phap Cho Cac Khau Robot (Cap Nhat Lan Cuoi) ---');
disp('----------------------------------------------------------------------------------');




mass_khau1_kg = 0.6068;
mass_khau2_kg = 1.3031;
mass_khau3_kg = 0.942;
mass_khau4_kg = 0.942;

mass_khau1_g = mass_khau1_kg * 1000;
mass_khau2_g = mass_khau2_kg * 1000;
mass_khau3_g = mass_khau3_kg * 1000;
mass_khau4_g = mass_khau4_kg * 1000;

% Dien tich mat cat ngang chung cho cac khau (theo yeu cau cua ban)
% Don vi: met vuong (m^2)
dien_tich_mat_cat_A = 0.03; % <--- Dien gia tri dien tich A cua ban vao day (don vi m^2)

% Gia toc trong truong (hang so)
g = 9.81; % m/s^2


% Kiem tra dieu kien dien tich
if dien_tich_mat_cat_A <= 0
    error('Loi: Dien tich mat cat phai la mot so duong lon hon 0.');
end

disp('Ket qua tinh toan:');
disp('----------------------------------------------------------------------------------');

% --- Tinh toan cho Khau 4 ---
% Khau 4: Ch?u tr?ng l??ng c?a chính nó.
luc_F_khau4 = mass_khau4_kg * g;
ung_suat_khau4 = luc_F_khau4 / dien_tich_mat_cat_A;

fprintf('--- Thong so Khau 4 ---\n');
fprintf('   Luc do trong luong tren Khau 4 = %.4f N\n', luc_F_khau4);
fprintf('   Ung suat phap tren Khau 4 = %.2f Pa (Pascal)\n', ung_suat_khau4);
fprintf('\n');

% --- Tinh toan cho Khau 3 ---
% Khau 3: Ch?u tr?ng l??ng c?a Khâu 3 + Khâu 4.
tong_mass_tren_khau3 = mass_khau3_kg + mass_khau4_kg;
luc_F_khau3 = tong_mass_tren_khau3 * g;
ung_suat_khau3 = luc_F_khau3 / dien_tich_mat_cat_A;

fprintf('--- Thong so Khau 3 ---\n');

fprintf('   Tong khoi luong chiu tai (Khau 3 + Khau 4) = %.4f kg\n', tong_mass_tren_khau3);
fprintf('   Tong luc do trong luong tren Khau 3 = %.4f N\n', luc_F_khau3);
fprintf('   Ung suat phap tren Khau 3 = %.2f Pa (Pascal)\n', ung_suat_khau3);
fprintf('\n');

% --- Tinh toan cho Khau 2 ---
% Khau 2: Ch?u tr?ng l??ng c?a Khâu 2 + Khâu 3 + Khâu 4.
tong_mass_tren_khau2 = mass_khau2_kg + mass_khau3_kg + mass_khau4_kg;
luc_F_khau2 = tong_mass_tren_khau2 * g;
ung_suat_khau2 = luc_F_khau2 / dien_tich_mat_cat_A;

fprintf('--- Thong so Khau 2 ---\n');
fprintf('   Tong khoi luong chiu tai (Khau 2 + Khau 3 + Khau 4) = %.4f kg\n', tong_mass_tren_khau2);
fprintf('   Tong luc do trong luong tren Khau 2 = %.4f N\n', luc_F_khau2);
fprintf('   Ung suat phap tren Khau 2 = %.2f Pa (Pascal)\n', ung_suat_khau2);
fprintf('\n');

fprintf('--- Dien tich mat cat ngang su dung cho cac khau: %.4f m^2 ---\n', dien_tich_mat_cat_A);
disp('--- Ket thuc chuong trinh ---');
