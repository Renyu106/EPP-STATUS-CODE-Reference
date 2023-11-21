# EPP 코드 (gTLD)

gTLD (Verisign, Centralnic etc..)의 EPP 코드 목록입니다

## 일반 메시지

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_SUCCESS_CODE | 1000 | Command completed successfully | created/updated/deleted Command가 성공적으로 처리됨 |
| EPP_COMMAND_FAILED | 2400 | Command did not return a status code | 내부 오류 |
| EPP_COMMAND_FAILED | 2400 | Internal error. | 처리되지 않은 내부 오류 |
| EPP_UNIMPLEMENTED | 2101 | Unimplemented | 요청된 Command 명령이 구현이 안됨 |
| EPP_COMMAND_FAILED_FATAL | 2500 | Internal error: Data service operation not configured. | EPP 서버 구성이 잘못됨 |
| EPP_COMMAND_FAILED | 2400 | Internal error: No connection to data service. | EPP 서버에서 내부 데이터 서비스에 연결이 안됨 |
| EPP_COMMAND_FAILED_FATAL | 2500 | Internal error: No prices received from data service. | 내부 데이터 서비스에서 응답 오류가 발생됨 |
| EPP_BILLING_FAILURE | 2104 | Insufficient credit. Domain cannot be created. | 계정에 충분한 예치금이 없어서, 도메인을 만들 수 없음 |
| EPP_BILLING_FAILURE | 2104 | Insufficient credit. Domain cannot be renewed. | 계정에 충분한 예치금이 없어서, 도메인을 연장할 수 없음 |
| EPP_UNKNOWN_COMMAND | 2000 | No command specified | EPP 요청에 지정된 명령이 없거나 알 수 없음 |
| EPP_COMMAND_SYNTAX_ERROR | 2001 | Bad command name | 지정한 Command에 잘못된 문자가 포함되어 있음 |
| EPP_UNKNOWN_COMMAND | 2000 | Unknown command | EPP 요청에 지정한 명령이 없거나 알 수 없음 |
| EPP_COMMAND_FAILED | 2400 | Command does not match endpoint or command data is missing | hello 및 logout Command에 빈 명령 태그가 있음 |
| EPP_COMMAND_USE_ERROR | 2002 | You need to login first. | Command를 실행하기전 로그인을 해야함 |

## Contact 정보 생성

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PARAMETER_MISSING_ERROR | 2003 | Value required for extension.dkhm:CVR | 회사, 공공 기관 및 협회의 경우 CVR을 지정해야함 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Parameter value policy error | 사용자 아이디는 AUTO_GENERATE 또는 FORCE_GENERATE여야함 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Contact already exists | 내부 오류, 이니셜을 기반으로 생성된 사용자 아이디가 이미 존재함 |
| EPP_SUCCESS_CODE | 1000 | Contact already exists. Please re-use. | 사용자 데이터가 데이터베이스에 이미 존재함, 기존 정보 재사용 요구 |
| EPP_SUCCESS_CODE | 1000 | Contact created. | 데이터베이스에 새 연락처가 생성됨 |

## Contact 정보 업데이트

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_COMMAND_FAILED | 2400 | Password change failed | 비밀번호를 변경 실패 |
| EPP_AUTHORIZATION_ERROR | 2400 | You need to login first. | Command를 실행하기전 로그인을 해야함 |
| EPP_AUTHORIZATION_ERROR | 2400 | You are not authorized to change password on that contact | 해당 연락처의 비밀번호를 변경할 권한이 없음 |
| EPP_AUTHORIZATION_ERROR | 2400 | Permission denied to change email | 해당 연락처의 이메일을 변경할 권한이 없음 |
| EPP_PENDING_CODE | 1001 | Command completed. Pending e-mail-address verification. | 이메일 주소 변경이 등록되어 확인 대기중 |
| EPP_AUTHORIZATION_ERROR | 2400 | You are not authorized to change that contact | 해당 연락처를 변경할 권한이 없음 |
| EPP_PROHIBITED_OPERATION | 2304 | You do not have permissions to modify field: %s | 사용자에게 수정할 권한이 없는 필드가 지정되어있음 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Invalid CVR number | 지정한 CVR 번호가 CVR 번호 지정과 일치하지 않음 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Name and CVR number does not match | 지정한 이름과 CVR 번호가 CVR에 등록된 데이터와 일치하지 않음 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | You need to specify pnumber | CVR 번호에 번호가 1개 이상 첨부된 경, 번호를 지정해야함 |
| EPP_COMMAND_FAILED | 2400 | Unable to verify CVR number. Please try again later. | 데이터 확인을 위해 CVR에 연결할 수 없음 |
| EPP_DATA_MANAGEMENT_POLICY_VIOLATION | 2308 | Multiple operations perfomed in one request: (%s) | 클라이언트가 동일한 요청에서 객체에 대해 여러 작업을 수행하려고 시도중임 |

## Contact 정보 조회

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2302 | Contact not found | 지정한 연락처가 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | Unauthorized | 사용자가 지정한 연락처의 정보를 볼 수 없음 |

## 도메인 생성

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Specifying contacts for registrar managed domains is not allowed | 등록기관 관리 도메인의 경우 연락처가 자동으로 할당됨 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Invalid period %s. Must be within range | 지정한 기간이 지원이 안됨 |
| EPP_AUTHORIZATION_ERROR | 2201 | Contact has previously failed ID control and cannot become registrant. | 지정한 연락처가 ID 제어에 실패하여 등록자가 될 수 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | Registrar handle is not permitted for registrant role. | REG-% 핸들은 등록자로 사용할 수 없음 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Invalid or inactive nameserver: %s | 지정한 네임서버가 유효하지 않거나 비활성 상태임 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | dkhm.autorenew ‘N’ not allowed with dkhm:management choice “registrant” | 등록자 처리 도메인에 대해 자동 갱신이 거짓일 수 없음 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Too few users for contact type | 지정한 연락처 수가 해당 연락처 유형에 대한 최소값 미만임 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Too many users for contact type | 지정한 연락처 수가 해당 연락처 유형에 대해 최대값을 초과임 |
| EPP_PENDING_CODE | 1001 | Create domain pending for %s | 도메인 신청이 수락되었으며 도메인이 생성 대기중임 |
| EPP_INVALID_AUTHORIZATION_INFORMATION | 2202 | Invalid authorization information | 등록자 사용자 아이디가 대기자 명단에 있는 사용자 아이디와 일치하지 않음 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Domain Name is occupied | 도메인이 이미 다른 사용자에 의해 등록되어 있음 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Parameter value policy error | 도메인 이름에 잘못된 문자가 포함되어 있거나 잘못된 형식임 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Bad value for dkhm:orderconfirmationToken: >%s< | 제공된 주문 확인 토큰에 잘못된 문자가 포함되어 있거나 잘못된 형식임 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | dkhm:orderconfirmationToken: >%s< exceeds allowed threshold | 제공된 주문 확인 토큰이 만료됨 |

## 도메인 업데이트

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Unable to resolve nameserver. | 제공된 네임서버 찾을 수 없음 |
| EPP_PARAMETER_MISSING_ERROR | 2003 | No nameservers supplied. | 제공된 네임서버 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | No nameserver host info. | 도메인에 정의된 네임서버 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | No NS info on host. | 네임서버에 대한 NS 정보 찾을 수 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Too few hosts. | 제공된 네임서버 수 하한 이하 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Too many hosts. | 제공된 네임서버 수 상한 초과 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Host is missing NS record when compared to other responses. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Host has extra NS record when compared to other responses. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | SOA Serial mismatch between responses. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | No nameservers found. | 도메인의 네임서버 찾을 수 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Host has alternating SOA serial between queries. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | IP address missing in nameserver IP address response | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Nameserver response contains non-public IP address | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Failed to query nameservers. Timed out. | 도메인에 대한 네임서버 쿼리 불가 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Problem with nameserver setup: (%s) not found. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Problem with nameserver setup. | 잘못 구성된 네임서버 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Failed to query nameservers. | 도메인에 대한 네임서버 쿼리 불가 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Specifying contacts for registrar managed domains is not allowed | 등록 기관에서 관리하는 도메인 연락처 자동 할당 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Domain does not exist | 존재하지 않는 도메인 업데이트 시도 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Remove “all” and specific keys not allowed in same operation. | 잘못된 매개변수 조합 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Change of registrant cannot be combined with other changes | 등록자 변경 별도 요청 필요 |
| EPP_PROHIBITED_OPERATION | 2304 | Bad userid. User is in a registrar group | 등록자 그룹 속한 사용자 등록자 지정 불가 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to change registrant | 사용자에게 등록자 변경 권한 없음 |
| EPP_COMMAND_USE_ERROR | 2002 | Command use error | 인증 정보에 대해 pw 및 null 모두 정의됨 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to set authinfo | 사용자에게 authinfo 설정 권한 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to unset authinfo | 사용자에게 인증 정보 설정 해제 권한 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to change auto_renew | 사용자에게 auto_renew 변경 권한 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to restore domain | 사용자에게 도메인 복원 권한 없음 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Parameter error. %s | 매개변수 사양 미충족, 오류 메시지 참조 |
| EPP_PENDING_CODE | 1001 | Command completed. Pending registrant accept | 작업 확인, 등록자 수락 대기 중 |
| EPP_PENDING_CODE | 1001 | Command completed. Pending registrant approval | 작업 확인, 등록자 승인 대기 중 |
| EPP_COMMAND_SYNTAX_ERROR | 2001 | Command syntax error | Authinfo 토큰, 도메인:null 또는 도메인:pw와 함께 autoredel 또는 autotransfer 사용 권장 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. | 사용자에게 요청된 작업 권한 없음 |
| EPP_AUTHORIZATION_ERROR | 2201 | Missing privilege | 사용자에게 요청된 작업 권한 없음 |
| EPP_PENDING_CODE | 1001 | Command completed successfully; action pending | VID 연락처 승인 대기 중 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Role not permitted | F 및 B 역할 제거 불가 |
| EPP_AUTHORIZATION_ERROR | 2201 | Repeated remove | 동일한 역할 두 번 이상 지정 |
| EPP_UNIMPLEMENTED_OBJECT_SERVICE | 2307 | Unimplemented object service | 요청된 작업 미구현 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | IP not supported for nameserver remove | 호스트 이름 대신 IP 주소로 네임서버 제거 지원 안 함 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Host not found: %s | 제거할 호스트 찾을 수 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Host / domain relation not found | 제거할 호스트 요청 도메인 네임서버 등록 안 됨 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Invalid or inactive nameserver: %s | 네임서버로 추가할 호스트 유효하지 않거나 비활성 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | To few active hosts | 네임서버로 추가할 호스트 중 일부 활성 등록됨 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Host / domain relation already exists | 네임서버로 추가할 호스트 요청 도메인 네임서버 이미 등록됨 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | IP not supported for nameserver add | 호스트 이름 대신 IP 주소로 네임서버 추가 지원 안 함 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Gluerecords required on new nameserver | 재위임에 GlueRecord 필요 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Nameserver changes required when specifying authinfo token | authinfo 토큰 지정 시 네임서버 변경 지정 필요 |
| EPP_PARAMETER_MISSING_ERROR | 2003 | Value required for authinfo.pw | authinfo.pw 미지정 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | No privilege. You are not NSA for all nameservers (old and new) | 사용자 요청된 모든 네임서버에 대해 NSA여야 함 |
| EPP_AUTHORIZATION_ERROR | 2201 | Nameserver Change failed | 누락된 권한으로 네임서버 변경 실패 |
| EPP_COMMAND_FAILED | 2400 | Server Error | 내부 오류 |
| EPP_COMMAND_FAILED | 2400 | Command failed | Command 처리 실패 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | DS set not found | 제거할 DS 레코드 찾을 수 없음 |
| EPP_UNIMPLEMENTED_OBJECT_SERVICE | 2307 | maxSigLife not supported | secDNS:maxSigLife 매개 변수 미지원 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Bad digest length | 지정한 다이제스트 길이 예상치 않음 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | DS set already exists | 추가할 DS 레코드 이미 존재 |
| EPP_BILLING_FAILURE | 2104 | Billing failure | 이 작업에 선불 계정 필요 |
| EPP_DATA_MANAGEMENT_POLICY_VIOLATION | 2308 | Multiple operations perfomed in one request: (%s) | 클라이언트 동일 요청에서 개체에 대해 여러 작업 시도 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | No DS records for domain | DS 레코드 할당되지 않은 도메인에 대한 DS 레코드 삭제 시도 |
| EPP_PROHIBITED_OPERATION | 2304 | Domain status prohibits operation | 도메인 현재 상태 DS 레코드 삭제 금지 |
| EPP_AUTHORIZATION_ERROR | 2201 | The given handle/user ID cannot be used as registrant | 상태 또는 사용자 ID로 등록자로 사용 불가 |
| EPP_AUTHORIZATION_ERROR | 2201 | The given handle/user ID cannot be used as registrant, due to missing/rejected ID control | 사용자 ID 제어 완료 필요 |

## 도메인 조회

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Domain not found | 도메인을 찾을 수 없음 |

## 도메인 삭제

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PROHIBITED_OPERATION | 2304 | Domain delete already pending. | 이미 도메인이 삭제 대기중임 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Parameter value policy error | 삭제 날짜가 거부되었음,
결제일까지 오늘 또는 그 이후가 아니여야함 |
| EPP_PENDING_CODE | 1001 | Command completed successfully; action pending | 삭제 대기중임 |

## 도메인 연장

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | The only supported unit is y | 새 기간에 대한 지원되는 단위는 오직 '년(y)'임 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Invalid period %s. Must be within range | 요청된 기간이 유효한 기간 범위 내에 있지 않음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Domain not found | 존재하지 않는 도메인을 갱신하려는 시도 |
| EPP_AUTHORIZATION_ERROR | 2201 | You do not have the privilege required to renew this domain | 도메인을 갱신하려면 사용자는 지불 담당자여야 함 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Given curExpDate %s does not match current expire date: %s | 지정된 만료일이 도메인의 만료일과 일치하지 않음 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | New expire date %s exceeds max %s | 새로운 만료일이 도메인의 최대 만료일을 초과함 |
| EPP_NOT_ELIGIBLE_FOR_RENEWAL | 2105 | Domain is not in a state where it can be renewed | 도메인은 구독 ID를 가져야 하며, 차단되지 않고, 활성 상태이며, 지불 완료되어야 하고, 만료되지 않아야 함 |
| EPP_COMMAND_FAILED | 2400 | Internal error. Domain cannot be renewed. | 도메인을 갱신하려고 시도 중 내부 오류가 발생함 |

## 도메인 기관이전

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Cannot change registrar on non-existent domain | 기관이전할 도메인 존재하지 않음 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege. You are not authorized to transfer domain | 사용자에게 도메인 기관이전 권한 부족 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Object is not registrar managed. | 등록자 등록자 처리 도메인 철회 불가 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Object is not ready for transfer at this time | 도메인에 아직 구독 ID 할당되지 않음, 나중에 다시 시도 권장 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Object is not eligible for transfer, payment status prohibits transfer | 도메인 지불되어야 함 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Object is not eligible for transfer, domain status prohibits transfer | 도메인이 차단됨 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Object is not eligible for transfer, domain status prohibits transfer | 새 등록기관에 아직 계정 번호 할당되지 않음, 나중에 다시 시도 권장 |
| EPP_AUTHORIZATION_ERROR | 2201 | Object is not eligible for transfer, no valid authinfo token | 유효한 인증 토큰 필요 |
| EPP_AUTHORIZATION_ERROR | 2201 | Object is not eligible for transfer, registrar not allowed to request registrar change | 등록자 등록기관 변경 요청 불가 |
| EPP_ASSOCIATION_PROHIBIT_OPERATION | 2305 | Not all domains in list have same registrant | 같은 작업에서 기관이전되는 모든 도메인 동일 등록자 소유여야 함 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege to become registrar | 사용자는 활성 등록기관이어야 함 |
| EPP_AUTHORIZATION_ERROR | 2201 | Change of registrar without authinfo token is not currently allowed | authinfo 토큰 없이 기관이전 가능한 전환 기간 종료 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Registrar group membership is required for this operation | 기관이전 수행 위해 사용자는 등록기관 그룹 회원이어야 함 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Domain has not yet been assigned a subscription id | 구독 ID 아직 할당되지 않음, 나중에 다시 시도 권장 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Domain has unpaid invoices | 기관이전전에 모든 청구서 지불 필요 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Domain is locked | 잠긴 도메인 기관이전 불가 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Domain is blocked | 차단된 도메인 기관이전 불가 |
| EPP_NOT_ELIGIBLE_FOR_TRANSFER | 2106 | Registrant has not been id validated | 등록자 ID 인증 수행 후 기관이전 재시도 권장 |
| EPP_AUTHORIZATION_ERROR | 2201 | Cannot change registrar for domain. Missing privilege | 사용자에게 등록기관 변경 권한 없음 |
| EPP_OBJECT_EXISTS | 2302 | Domain is already registrar managed. | 전환 기간 동안 토큰 없이 기관이전은 등록자 처리 도메인에만 해당 |
| EPP_ASSOCIATION_PROHIBIT_OPERATION | 2305 | No NSA for domain is member of this registrar group | 전환 기간 동안 토큰 없이 기관이전 시 NSA는 등록기관 그룹에 속해야 함 |
| EPP_INVALID_AUTHORIZATION_INFORMATION | 2202 | Supplied authinfo token is not valid for this domain/operation | 제공된 authinfo 토큰 무효 |
| EPP_AUTHORIZATION_ERROR | 2201 | Domain transfer failed | 전환 기간 동안 토큰 없이 기관이전 시 NSA는 등록기관 그룹에 속해야 함 |
| EPP_COMMAND_FAILED_FATAL | 2500 | Error occoured taking registrar role | 도메인 기관이전 중 내부 오류 발생 |
| EPP_ASSOCIATION_PROHIBIT_OPERATION | 2305 | Object is not handled by current user | 사용자 다른 사용자 처리 도메인에서 철회 불가 |

## Glue Record(Host) 생성

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PARAMETER_POLICY_ERROR | 2306 | Registrar handle not permitted as NSA | 등록기관 핸들은 NSA가 될 수 없음 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Host name already exists | 이미 생성된 네임서버 생성 시도 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Host already exists | 이미 생성된 네임서버 생성 시도 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Invalid host name. | 네임서버에 대한 지정된 이름 유효하지 않은 호스트 이름 |
| EPP_PARAMETER_SYNTAX_ERROR | 2005 | Invalid TLD in host name. | 지정된 호스트 이름의 최상위 도메인 이름 무효 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Domain does not exist | 네임서버에 대한 도메인 이름 존재하지 않음 |
| EPP_PARAMETER_POLICY_ERROR | 2306 | NSA not in registrar group | 새 네임서버에 대한 지정된 NSA는 등록기관 그룹에 속해야 함 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege | 사용자에게 네임서버 생성 권한 없음 |
| EPP_PENDING_CODE | 1001 | Command completed. Pending registrant approval. | 네임서버 등록됨, 등록기관 승인 대기 중 |
| EPP_PENDING_CODE | 1001 | Command completed. Pending approval by nameserver contact | 네임서버 등록됨, 네임서버 연락처 승인 대기 중 |

## Glue Record(Host) 업데이트

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_PARAMETER_POLICY_ERROR | 2306 | REG handle not permitted for requestedNsAdmin | 등록기관 핸들은 NSA가 될 수 없음 |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2303 | Unknown host | 업데이트할 네임서버 존재하지 않음 |
| EPP_OBJECT_EXISTS_ERROR | 2302 | Host already exists | 이미 사용 중인 새 이름으로 네임서버 이름 변경 시도 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege | 사용자에게 IP 주소 추가/제거 또는 존 연락처 변경 권한 없음 |
| EPP_PROHIBITED_OPERATION | 2304 | Not enough ip addresses after change. Minimum one needed. | 네임서버에 최소 1개의 IP 주소 필요 |
| EPP_UNIMPLEMENTED_SERVICE | 2307 | Unimplemented command | 네임서버 호스트 이름 변경 미구현 |
| EPP_PARAMETER_RANGE_ERROR | 2004 | Host IP address already exists | 할당된 IP 주소 이미 사용 중 |
| EPP_PENDING_CODE | 1001 | Command completed successfully; action pending | 업데이트 등록됨, NSA 승인 대기 중 |
| EPP_DATA_MANAGEMENT_POLICY_VIOLATION | 2308 | Multiple operations perfomed in one request: (%s) | 클라이언트, 동일 요청에서 개체에 대해 여러 작업 시도 |

## Glue Record(Host) 조회

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2302 | Host not found | 존재하지 않는 네임서버에 대한 정보 요청 시도 |

## Glue Record(Host) 삭제

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2302 | Host does not exist | 존재하지 않는 네임서버 삭제 시도 |
| EPP_ASSOCIATION_PROHIBIT_OPERATION | 2305 | Nameserver has active domains, cannot be deleted | 사용 중인 네임서버 삭제 불가 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege | 사용자에게 이 네임서버 삭제 권한 없음 |

## 예치금 조회

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2302 | Contact not found | 잔액 조회 요청한 연락처 존재하지 않음 |
| EPP_AUTHORIZATION_ERROR | 2201 | Unauthorized | 요청한 사용자의 잔액 조회 권한 사용자에게 없음 |

## 로그인

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_COMMAND_FAILED | 2400 | Internal error: IP address missing | EPP 서버 클라이언트 IP 주소 확인 불가 |
| EPP_AUTHORIZATION_ERROR | 2201 | No privilege | 다른 사용자의 비밀번호 변경 불허 |
| EPP_PARAMETER_MISSING_ERROR | 2003 | Please specify login user and password. | 로그인 시 사용자 이름과 비밀번호 필요 |
| EPP_COMMAND_USE_ERROR | 2002 | Repeated logins are not permitted. | 사용자 이미 로그인 상태 |
| EPP_AUTHENTICATION_ERROR | 2200 | Login failed | 유효하지 않은 사용자 이름 또는 비밀번호 |

## 로그아웃

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_SUCCESS_DISCONNECT | 1500 | Not logged in, or already logged out | User is not logged in |
| EPP_SUCCESS_DISCONNECT | 1500 |  | User logged out |

## 폴

| 상태 | 상태코드 | 상태 메시지 | 설명 |
| --- | --- | --- | --- |
| EPP_OBJECT_NOT_EXISTS_ERROR | 2302 | Object does not exist | 확인된 메시지 ID 존재하지 않음 |
| EPP_SUCCESS_ACK_DEQUEUE | 1301 | Command completed successfully; ack to dequeue | 메시지 성공적으로 가져옴, 메시지 대기열에서 제거하려면 ACK 보내야 함 |
| EPP_SUCCESS_NO_MSG | 1300 | Command completed successfully; no messages | 대기열에 메시지 없음 |
